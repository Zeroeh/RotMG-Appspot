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

Firstly you need to download a fuzzer. I will be using [ffuf](https://github.com/ffuf/ffuf) as it is powerful and fast. After you downloaded it from [Releases](https://github.com/ffuf/ffuf/releases) you are ready to start. Here is the command we are going to use for fuzzing:
```sh
ffuf.exe -u https://realmofthemadgodhrd.appspot.com/FUZZ/ -mr "The resource could not be found." -w wordlist.txt
```
You should enter path to your wordlist after the `-w` keyword (you may find them [here](https://github.com/search?q=wordlist+fuzzing))

That's it! No more configuration is required. Now you should just sit back and relax. When the results will be ready you should see if they wasn't already listed here. If you find something new open an issue or create Pull Request.
