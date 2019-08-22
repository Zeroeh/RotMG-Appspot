If you have any contributions (new urls, previously unknown parameters, ect), feel free to submit an issue or pull request and I will be sure to credit you. **Hey! Don't forget to check the new CONTRIBUTE.md guide**

The main goal of this project is to document endpoints in the RotMG appspot API. All links (at least the ones we can find), old or new, are posted here.

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

``app/``
 * ``globalNews``
 * ``getLanguageStrings`` => gameClientVersion, languageType
 * ``init``

``package/``
 * ``getPackages`` => guid, password

``mysterybox/``
 * ``getBoxes`` => returns error

``credits/``
 * ``getoffers``
 * ``pwpurchase``
 * ``add``
 * ``done``
 * ``error``
 * ``kabamadd`` => no longer exists
 * ``token``

``picture/`` => Seems to redirect to google login now
 * ``list``
 * ``get``

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
 * ``logFteStep`` => returns an error

``server/`` => all of these urls are internal
 * ``list``
 * ``add``
 * ``remove``

``account/``
 * ``register`` => newPassword, entrytag, newGUID, isAgeVerified, guid, ignore
 * ``verify`` => guid, password (used by Muledump)
 * ``verifyage`` => guid, password
 * ``acceptTOS`` => guid, password
 * ``changeEmail``
 * ``playFortuneGame`` => id (likely)
 * ``rp``
 * ``login``
 * ``setName`` => guid, password, name
 * ``validateEmail`` (removed, changed to isEmailVerified)
 * ``supportVerify`` => guid, password, secret
 * ``*addStar``
 * ``*addIgnore``
 * ``purchaseCharSlot`` => guid, password
 * ``*purchaseVaultChest``
 * ``purchaseSkin`` => guid, password, (skin?)
 * ``purchaseMysteryBox`` => guid, password, id
 * ``purchasePackage`` => guid, password, id
 * ``getOwnedPetSkins`` => guid, password
 * ``getBeginnerPackageTimeLeft`` (removed)
 * ``sendVerifyEmail`` => guid, password
 * ``forgotPassword`` => guid
 * ``changePassword`` => newPassword, &ignore, guid, password, &gameClientVersion
 * ``getCredits`` => guid, password
 * ``*ban``
 * ``v`` => a, action, g-recaptcha-response
 * ``*claimLoginReward``
 * ``saveSecurityQuestions`` => guid, password
 * ``forgotpasswordPage`` => links to a page where you enter your email
 * ``isEmailVerified``

``supportCampaign/``
 * ``claim`` => guid, password
 * ``unlock`` => guid, password
 * ``donate`` => guid, password, amount
 * ``status`` => guid, password
 
``fame/``
 * ``list`` => timespan(week, month, all), &ignore, &charId, &gameClientVersion, &accountId

``dailyLogin/``
 * ``fetchCalendar`` => guid, password

``dailyquest/``
 Looks like a regular stub, but it may be dangerous for account
 * ``resetDailyQuests`` => guid, password (returns this error: This feature is disabled. Your attempt of using it was noted)
 * ``resetDailyQuestsAdmin``

``char/``
 * ``list`` => guid, password
 * ``fame`` => accountId, charId
 * ``*purchase``
 * ``*get``
 * ``*reskin``
 * ``*create``
 * ``*update``
 * ``purchaseClassUnlock``
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
 * ``listMembers`` => guid, password

``kabam/``
 * ``getcredentials`` => userId
 * ``link``
 * ``verify``

``migrate/``
 * ``doMigration``
 * ``progress`` => guid
 * ``userAccountReset``

``steamworks/``
 * ``finalizePurchase``
 * ``getcredentials`` => userId
 * ``purchaseOffer``
 * ``register`` (disabled)
 * ``link`` (disabled)

``kongregate/``
 * ``getcredentials`` => userId
 * ``register`` => userId
 * ``link`` (disabled)
 * ``internalRegister``

``clientError/``
 * ``add``

``ugc/`` (User Generated Content)
 * ``save`` => name, description, thumbnail

``sfx/``
 * => too many mp3 files to list (you can find these in pserver sources)
 
``music/``
 * ``sorc.mp3`` => main theme for realm

Unknown urls

Payment url: http://www.realmofthemadgod.com/?user_id=email&status=done&invoice_id=111111111
