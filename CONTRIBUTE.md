# This guide is about contributing and finding new links

## Finding new links
-  Download Fiddler trial from [offical site](https://www.telerik.com/download)
-  Install it just by pressing Next button all the time
-  Open it and go to Tools > Options > HTTPS > enable `Decrypt HTTPS traffic`
-  Install all the certificates
-  Open Realm of the Mad God and play it. Then check all the URLs and their parameters in Fiddler
-  If you find something interesting open an issue or create Pull Request

## Checking links
This process may take some time but is very useful because DECA removes urls quite often
-  Open `README.md` file, copy the root url and paste it in the new browser window
-  Add sections like `friends` or `arena` to URL
-  Add required parameters and open this URL
-  If you see any error about missing parameters, message about removed link or something unmentioned in `README.md` open an issue or create Pull Request

## Finding new subdirectories
Finding subdirectories is quite fun, as it opens up a door to potentially a bunch of new urls. It's recommended to use some sort of web crawler or name generator rather than finding these by hand, but if you're smart and know the game topology, finding them by hand can be just as effective.
I created some graphics that should demonstrate how easy it is to get started.
The first image is the result of a subdirectory that does not exist.
![Screenshot](/pics/false.png)

Subdirectories that do not exist should give out a "not found" error, but not a "404" error.

The following image shows a subdirectory that exists. Notice the smaller font and the inclusion of "404".
![Screenshot](/pics/true.png)

If you find one of these that are not already listed in the README.md, please submit an issue with your discovery.

This next image shows what happens when you forget to add the extra "/" at the end of the url.
![Screenshot](/pics/badinput.png)

If you forget to add the backslash you could potentially be wasting time or worse, may have even found a directory.

### Using URL Fuzzer
The URL Fuzzer can be used to find hidden files and directories on a web server by fuzzing.
This is a discovery activity which allows you to discover resources that were not meant to be publicly accessible (ex. /backups, /index.php.old, /archive.tgz, /source_code.zip, etc). We are going to use URL fuzzing for finding new subdirectories.

Firstly you need to download a fuzzer. I will be using [ffuf](https://github.com/ffuf/ffuf) as it is powerful and fast. After you downloaded it from [Releases](https://github.com/ffuf/ffuf/releases) you are ready to start. his is the command we are going to use for fuzzing:
```sh
ffuf -c -u https://realmofthemadgodhrd.appspot.com/FUZZ/ -w wordlist.txt
```
You should enter path to your wordlist after the `-w` keyword (you may find them [here](https://github.com/search?q=wordlist+fuzzing))

That's it! No more configuration is required. Now you should just relax and wait when the fuzzer finishes its work. After that you should see if there were any results and if there are, check if they are not already listed here. If you find something new open an issue or create Pull Request.

Also if you want to catch another response codes like Forbidden (though they are mostly useless), you should use this command:
```sh
ffuf -c -u https://realmofthemadgodhrd.appspot.com/FUZZ/ -mc 100,101,102,200,201,202,203,204,205,206,207,208,226,300,301,302,302,303,304,305,306,307,308,400,401,402,403,405,406,407,408,409,410,411,412,413,414,415,416,417,418,419,421,422,423,424,426,428,429,431,449,451,452,499,500,501,502,503,504,505,506,507,508,509,510,511,520,521,522,523,524,525,526 -w wordlist.txt
```
