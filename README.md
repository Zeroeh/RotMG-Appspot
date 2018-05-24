If you have any contributions (new urls, previously unknown parameters, ect), feel free to submit an "issue"
 (**not** a pull request) and I will add it to this archive.


root url: http://realmofthemadgodhrd.appspot.com/

directories marked with an asterisk (*) are internal server urls and will always return "\<Failure/\>"

directories marked with a dollar sign ($) do not take any parameters (or they are not known)

parameters marked with an ampersand (&) are OPTIONAL parameters and can be excluded from the url

parameters marked with a percent sign (%) are GLOBAL parameters and can seemingly be used in any valid url

Please note that deca can add or remove links at any time, and will certainly remove links posted here.

## Testing Links
(http://rotmghrdtesting.appspot.com)
(http://rotmgtesting.appspot.com)
(http://realmtesting2.appspot.com)

**/**
 * $logowtext.png
 * $realmlogo.png
 * version.txt => time
 * servers.txt
 * crossdomain.xml
 * draw.html
 * TMloader(version).swf
 * TextureMaker(version).swf
 * AGCloader.swf
 * $AssembleeGameClient(version).swf

**app/**
 * $globalNews
 * getLanguageStrings => gameClientVersion, languageType
 * init

**package/**
 * getPackages => guid, password

**mysterybox/**
 * getBoxes

**credits/**
 * getoffers
 * pwpurchase
 * add
 * done
 * error
 * kabamadd => no longer exists

**picture/**
 * list
 * get

**images/**
 * DecaLogoWhite.png
 * kabamLogo192x97.png

**css/**
 * rotmg.common.css?__rotmg_cb=1424381358

**js/**
 * rotmg.UrlLib.js
 * rotmg.Paymentwall.js
 * jquery-1.8.0.min.js
 * rotmg.Xsolla.js

**admin/**
 * => redirects to google app engine sign in

**data/**
 * => prints a message saying you are forbidden to access this page

**log/**
 * logFteStep => returns an error

**server/**
 * => all of these urls are internal
 * list
 * add
 * remove

**account/**
 * register
 * verify
 * verifyage
 * acceptTOS
 * changeEmail
 * playFortuneGame
 * resetPassword
 * login
 * setName
 * validateEmail
 * supportVerify => guid, password, secret
 * *addStar
 * *addIgnore
 * purchaseCharSlot
 * *purchaseVaultChest
 * purchaseSkin
 * purchaseMysteryBox
 * purchasePackage
 * getBeginnerPackageTimeLeft
 * sendVerifyEmail
 * forgotPassword
 * changePassword => newPassword, &ignore, guid, password, &gameClientVersion
 * getCredits
 * *ban
 * v => a, b
 * *claimLoginReward
 * saveSecurityQuestions

**fame/**
 * list => timespan(week, month, all), ignore, charId, gameClientVersion, accountId

**dailyLogin/**
 * fetchCalendar => guid, password

**dailyquest/**
 * resetDailyQuests => returns a message saying your ip was logged.

**char/**
 * list => guid, password
 * fame => accountId, charId
 * *purchase
 * *get
 * *reskin
 * *create
 * purchaseClassUnlock
 * delete => password, gameClientVersion, charId, reason (seems to be always 1), guid, ignore

**inGameNews/**
 * getNews

**friends/**
 * requestFriend => ignore, guid, targetName, password, gameClientVersion
 * getList => ignore, guid, gameClientVersion, password
 * getRequests => ignore, guid, gameClientVersion, password
 * acceptRequest => ignore, guid, targetName, gameClientVersion, password
 * rejectRequest => ignore, guid, targetName, gameClientVersion, password
 * removeFriend => ignore, guid, targetName, gameClientVersion, password
 * blockRequest => ignore, guid, targetName, password, gameclientVersion

**pet/**
 * *feed
 * *fuse

**news/**
 * => takes you to google sign in

**arena/**
 * getRecords => ignore, type(weekly, personal, alltime), guid, password, gameClientVersion
 * getPersonalBest

**guild/**
 * *changeRank
 * *removeMember
 * *create
 * getBoard => guid, password
 * setBoard => guid, password, board
 * listMembers

**kabam/**
 * getcredentials => userId
 * link

**migrate/**
 * doMigration
 * progress
 * userAccountReset

**steamworks/**
 * finalizePurchase
 * getcredentials => userId
 * purchaseOffer
 * register
 * link

**kongregate/**
 * getcredentials => userId
 * register
 * link

**clientError/**
 * add

**ugc/**
 * save

**sfx/**
 * => too many mp3 files to list (you can find these in pserver sources)

Unknown payment url: http://www.realmofthemadgod.com/?user_id=email&status=done&invoice_id=111111111
