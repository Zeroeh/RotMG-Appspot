If you have any contributions (new urls, previously unknown parameters, ect), feel free to submit an issue or pull request and I will be sure to credit you. **Feel like helping? Don't forget to check the new CONTRIBUTE.md guide**

The main goal of this project is to document endpoints in the RotMG appspot API. All links (at least the ones we can find / have access to), old or new, are posted here.

## Root URL
- https://realmofthemadgodhrd.appspot.com
- https://realmofthemadgod.appspot.com (used before kabam account migration)

## Testing Links
- https://rotmghrdtesting.appspot.com (old kabam test server used for account migration testing)
- https://rotmgtesting.appspot.com (the current rotmg testing server)
- https://realmtesting2.appspot.com ("hidden" testing server for private testers)
- https://test3.realmofthemadgod.com (Unknown)
- https://rotmgtesting3.appspot.com
- https://test.realmofthemadgod.com
- https://testing.realmofthemadgod.com

Directories marked with an asterisk (*) are internal server urls and will always return ``<Failure/>``

Endpoints without any listed arguments could still take certain parameters, but they might not be listed here yet due to incompletedness.

Please note that deca can add or remove links at any time.

**Known URL parameters** (Sorted by key:value, or example value)
- `game_net`:`rotmg`
- `game_net_user_id`: _empty_
- `ignore`:`23424` _random number from 1000 to 999999_ (used for cache busting)
- `gameClientVersion`:`X31.2.3` (current game version)
- `languageType`:`en`
- `guid`:`example@mail.com` (email)
- `password`:`password123`

``/``
 * ``logowtext.png``
 * ``realmlogo.png``
 * ``version.txt`` => time (unix time)
 * ``servers.txt``
 * ``crossdomain.xml``
 * ``draw.html`` => Removed
 * ``TMLoader{version}.swf`` => Removed
 * ``TextureMaker{version}.swf`` => Removed
 * ``AGCloader.swf``
 * ``client``
 * ``AssembleeGameClient{version}.swf``
 * ``playerProductInstall.swf``
 * ``UGDTermsofUse.html``
 * ``kongregate.html``

``app/``
 * ``globalNews``
 * ``getLanguageStrings`` => gameClientVersion, languageType
 * ``init``

``package/``
 * ``getPackages`` => guid, password, language, version

``mysterybox/``
 * ``getBoxes`` => guid, password, version (seems to accept any float like 1.0)

``credits/``
 * ``getoffers``
 * ``pwpurchase`` => iframeUrl (json with these params: token, production)
 * ``add`` => tok, exp, guid, provider, jwt, price, paymentid
 * ``done``
 * ``error``
 * ``kabamadd`` => naid, signedRequest, createdat
 * ``token`` => guid, password

``picture/`` => Seems to redirect to google login now
 * ``list``
 * ``get`` => id, time
 * ``save``

``images/``
 * ``DecaLogoWhite.png``
 * ``kabamLogo192x97.png``

``css/``
 * ``rotmg.common.css?__rotmg_cb=1424381358``

``js/``
 * ``rotmg.UrlLib.js``
 * ``rotmg.Paymentwall.js``
 * ``jquery-1.8.0.min.js``
 * ``rotmg.Xsolla.js``

``admin/``
 * => redirects to google app engine sign in

``data/``
 * => prints a message saying you are forbidden to access this page

``log/``
 * ``logFteStep`` => game_net_user_id, game_net, play_platform, guid, password, fteStepCompleted (used for tracking tutorial progress, returns an error)
 * ``logGameModePlayed`` => seasonID (Public Testing Season), gameMode (Legacy or Challenger), guid, password

``server/`` => all of these urls are internal
 * ``list``
 * ``add``
 * ``remove``

``account/``
 * ``register`` => newPassword, entrytag, newGUID, isAgeVerified, guid, ignore, signedUpKabamEmail (0 or 1)
 * ``verify`` => guid, password (used by Muledump)
 * ``verifyage`` => guid, password
 * ``acceptTOS`` => guid, password
 * ``changeEmail`` => guid, password, newGuid
 * ``playFortuneGame`` => choice, status, currency (2 for fortune tokens or 0 for gold)
 * ``rp``
 * ``login``
 * ``setName`` => guid, password, name
 * ``validateEmail`` (removed, changed to isEmailVerified)
 * ``supportVerify`` => guid, password, secret
 * ``*addStar``
 * ``*addIgnore``
 * ``purchaseCharSlot`` => guid, password
 * ``*purchaseVaultChest``
 * ``purchaseSkin`` => guid, password, skinType
 * ``purchaseMysteryBox`` => guid, password, boxId, quantity, price, currency
 * ``purchasePackage`` => guid, password, boxId, quantity, price, currency
 * ``getOwnedPetSkins`` => guid, password
 * ``getBeginnerPackageTimeLeft`` => guid, password (removed)
 * ``sendVerifyEmail`` => guid, password
 * ``forgotPassword`` => guid
 * ``changePassword`` => newPassword, &ignore, guid, password, &gameClientVersion
 * ``getCredits`` => guid, password
 * ``*ban``
 * ``v`` => a, action, g-recaptcha-response
 * ``*claimLoginReward``
 * ``saveSecurityQuestions`` => guid, password, answers (encoded in base64 and split by a pipe operator [|])
 * ``forgotpasswordPage`` => links to a page where you enter your email
 * ``isEmailVerified`` => guid, password
 * ``signupDecaEmail`` => notifyMe (1 or 0), guid, password, email

``supportCampaign/``
 * ``claim`` => guid, password
 * ``unlock`` => guid, password
 * ``donate`` => guid, password, amount
 * ``status`` => guid, password
 * ``create``
 
``fame/``
 * ``list`` => timespan(week, month, all), &ignore, &charId, &gameClientVersion, &accountId
 * ``challengerSeasonList`` => guid, password
 * ``challengerLeaderboard`` => accountId, charId, timespan (same as fame/list)
 * ``challengerAccountLeaderboard`` => accountId, charId, timespan (same as fame/list)

``dailyLogin/``
 * ``fetchCalendar`` => guid, password

``season/``
 * ``getSeasons`` => guid, password, gameClientVersion

``dailyquest/``
 Looks like a regular stub, but it may be dangerous for account
 * ``resetDailyQuests`` => guid, password (returns this error: This feature is disabled. Your attempt of using it was noted)
 * ``resetDailyQuestsAdmin`` => guid, password

``char/``
 * ``list`` => guid, password, [challenger (false/true)][muleDump (true/false)]
 * ``fame`` => accountId, charId
 * ``*purchase``
 * ``*get``
 * ``*reskin``
 * ``*create``
 * ``*update``
 * ``purchaseClassUnlock`` => guid, password, game_net_user_id, game_net, play_platform, do_login, classType
 * ``delete`` => guid, password, gameClientVersion, charId, reason (seems to be always 1), ignore

``inGameNews/``
 * ``getNews``

``friends/``
 * ``requestFriend`` => ignore, guid, targetName, password, &gameClientVersion
 * ``getList`` => ignore, guid, gameClientVersion, password
 * ``getRequests`` => ignore, guid, gameClientVersion, password
 * ``acceptRequest`` => ignore, guid, targetName, gameClientVersion, password
 * ``rejectRequest`` => ignore, guid, targetName, gameClientVersion, password
 * ``removeFriend`` => ignore, guid, targetName, gameClientVersion, password
 * ``blockRequest`` => ignore, guid, targetName, password, gameclientVersion

``pet/``
 * ``*feed``
 * ``*fuse``

``news/``
 * => takes you to google sign in

``arena/``
 * ``getRecords`` => ignore, type(weekly, personal, alltime), guid, password, gameClientVersion
 * ``getPersonalBest`` => guid, password

``guild/``
 * ``*changeRank``
 * ``*removeMember``
 * ``*create``
 * ``getBoard`` => guid, password
 * ``setBoard`` => guid, password, board
 * ``listMembers`` => guid, password, num, offset
 * ``*purchase``

``kabam/``
 * ``getcredentials`` => userId, signedRequest, entrytag
 * ``link`` => kabamemail, kabampassword, email, password
 * ``verify`` => kabamemail, kabampassword

``migrate/``
 * ``doMigration`` => guid, password
 * ``progress`` => guid
 * ``userAccountReset`` => guid, password

``steamworks/``
 * ``finalizePurchase`` => appid, orderid, authorized (1 or 0)
 * ``getcredentials`` => userId
 * ``purchaseOffer`` => steamid, data
 * ``register`` => newGUID, newPassword, entrytag (disabled)
 * ``link`` (disabled)

``kongregate/``
 * ``getcredentials`` => userId
 * ``register`` => userId, username, gameAuthToken, newGUID, newPassword, entrytag
 * ``link`` (disabled)
 * ``internalRegister`` => userId, username, gameAuthToken, guid

``clientError/``
 * ``add`` => text, guid

``ugc/`` (User Generated Content)
 * ``save`` => guid, password, name, description, width, height, mapjm, tags, totalObjects, totalTiles, thumbnail, overwrite (on or off) (seems to always return <Error>Invalid permissions</Error>)
 * ``get``

``sfx/``
 * => too many mp3 files to list (you can find these in pserver sources)
 * See: https://realmofthemadgod.fandom.com/wiki/Sounds
 
``music/``
 * ``sorc.mp3`` => main theme for realm

## Unknown urls

Payment url: http://www.realmofthemadgod.com/?user_id=email&status=done&invoice_id=111111111
