# *nix Scavenger Hunt

Complete the following challenges using the command-line interface on your favorite
Unix or Linux operating system. You are welcome and encouraged to consult any
additional documentation online or in books.

Please add your answers/responses/text pastes to the document after each prompt.

Note: For some of the challenges you will need to reference files included with
this repository, so you will need to fork the repo into your own Github account
and then clone it to your development environment.

## The Challenges

### Navigating the Filesystem

* Get an idea of where you are in the operating system. Use the `pwd` command to find your "path to working directory"--your current location in the filesystem of your devbox. * Paste the output of the `pwd` command here: * 

```Shell
Bryans-MacBook-Air:wats1030-intro-to-unix bryan$ pwd
/Users/bryan/web-projects/seattle-university/wats1030-intro-to-unix
```

* Discover more about this filesystem. Use `ls` (the "list" command)to see what is in this directory. *What directories and files do you see when you run `ls`?*

```Shell
Bryans-MacBook-Air:wats1030-intro-to-unix bryan$ ls
LICENSE     challenge_files           nix_scavenger_hunt_stretch.md
README.md   nix_scavenger_hunt.md     super_scavengers.md
```

* You can use *options* to modify how a command runs. Try using `ls -alh` to see the contents of your current directory. *How are the results different when you use the `-alh` options?* 

> It's a much longer list which seems to include date last accessed, types of file names, and some kind of read/write
> information about the files.

 
* The `man` ("manual") command tells you more about how any given command works. (*WARNING:* CodeAnywhere does not support the man command. You can click the following link to complete this task: http://linux.die.net/man/). Run `man` to see instructions about how to use `man`. Then use `man` to learn what the `a`, `l`, and `h` options mean when used with the `ls` command. *Write down what those options do?*

> -a, --all
> do not ignore entries starting with .

> -h, --human-readable
> with -l, print sizes in human readable format (e.g., 1K 234M 2G)

> -l
> use a long listing format

* Commands can also take *arguments*, which are usually the names of files or locations that you want the command to work with. Try running `ls /` to see what files are in the *root* directory of the filesystem. *What files and directories do you see listed?*



* A Unix filesystem has a few special shortcuts to refer to specific locations. `/` indicates the *root* of the filesystem, meaning the top-most directory in the filesystem hierarchy. Use the `cd` ("change directory") command to move to the root directory. (Hint: Use `man` to look up the `cd` command if you have any issues) *Then run `pwd` and paste the output here:*
* Another special shortcut in Unix is the `~` location. This indicates the *user root* directory, meaning the top-most directory in the hierarchy that comes below your user account. Use `cd` to move to `~`. *Run `pwd` and paste the response here:*
* Change directory into the `challenge_files` directory. Use `ls` to find only the files with a `.demo` pattern. *How many files do you find?*

> Using 'ls -X', I sorted the files by extension and found three with .demo
```
2015_special_stuff.demo
cloaked-wookie.demo
scooter-double-mamba.demo
```

* Use the `cd` command to move "up" one directory. *Where are you in the filesystem now?*

```Shell
cabox@box-codeanywhere:~/workspace/challenge_files$ cd ..
cabox@box-codeanywhere:~/workspace$
```

* Press the up arrow on your keyboard. *What just happened?*

> The last command I typed ('cd ..') reappeared in the terminal.

* Press the up arrow a few more times. *What do you see?*

> The terminal is bringing up my last used commands!

* Run the `history` command. *What do you see?*

> I see a list of my last 11 used commands. Very cool.

### Observing the System

* Discover what account you are logged into using the `whoami` command. *What username are you currently using?*

```Shell
cabox@box-codeanywhere:~/workspace$ whoami
cabox
```
> (P.S., I've been switching back and forth between CodeAnywhere and my local machine using VS Code for this assignment.)

* Discover who else is on your system with the `who` command. *Are any other users using your system? If so, list them here:*

```Shell
cabox@box-codeanywhere:~/workspace$ who
cabox    pts/0        Oct 10 16:46 (52.161.27.120)
```

> From what I can tell, my Dev Box is the only "user" of this system. 

* How long has your system been running? Use `uptime` to see, and *paste the result here:*

```Shell
cabox@box-codeanywhere:~/workspace$ uptime
 17:02:12 up 26 min,  1 user,  load average: 0.00, 0.00, 0.00
```
* Run `ps aux` and review the results. (Hint: Use `man` to learn more about the `ps` command and options.) *How do you interpret what you see here?*

> The output of this command reminds me of running Ctrl-Alt-Delete and viewing the task manager on a machine running Windows 
> OS.

* Run `top` and review the results. (Hint: You may need to use `ctrl-c` to get out of this app.) *How do you interpret what you see here?*

> This looks even MORE like the task manager I remember using if my computer froze when I was growing up.
> It seems to show how much CPU power and RAM is being used as a percentage out of 100. It also shows a column for "virtual memory".
> Additionally, there's a "PID", which I'm guessing means Process ID, as well as a column which lists the user of the process. 
> On my CodeAnywhere devbox, the majority of the processes are used by "root", with about 5 more used by "cabox" (CodeAnywhere > box), and one being used by 'syslog'.


### Finding and Viewing Files

* Make sure you are in the `challenge_files` directory. Use the `*` wildcard to find all the files that have the word "credit" in the filename. *How many files did you find?*

> I found two files... 
> 'credit_cards.txt' and 'credit_cards2.txt'

* Use the `more` command to view one of the `credit_cards` files you just discovered. (Hint: Type `q` to quit viewing the file. Press the `spacebar` to page down. Use your keyboard arrows to move up/down.) *What is the date in the file you have viewed?*

```Shell
Bryans-MacBook-Air:challenge_files bryan$ more credit_cards.txt
Last updated: 01-15-2015
```
> (followed by a long list of numbers, presumably credit card numbers)

* Use the `find` command to search for files more effectively. Search the sub-directories under `challenge_files` to find the location of the file named `modi_laboriosam.txt`. *Where is that file located?*

```Shell
Bryans-MacBook-Air:challenge_files bryan$ find . -name modi_laboriosam.txt
./tmp/modi_laboriosam.txt
```
> It's located in the challenge_files/tmp/ directory.

* Use the `grep` command to search for text within a file. Use `grep` on all the `.user` files in `challenge_files` to find which files contain "WA" (the abbreviation for Washington state). *How many files did you find?*

```Shell
Bryans-MacBook-Air:challenge_files bryan$ grep "WA" *.user
Britt-Erdman.user:O'Harachester, WA 37261
Lissie-Strosin.user:Jewessfurt, WA 00816-7241
```

* Use the `-r` option of `grep` to *recursively* find the text "Waldo" hidden in a file somewhere under the `challenge_files` directory. *Paste the result showing the file and line where the word "Waldo" shows up.*

```Shell
Bryans-MacBook-Air:challenge_files bryan$ grep -r -n --color "Waldo" .
./serial-numbers/eaque_molestiae.txt:4:Ut est maiores quia autem. Nisi modi Waldo sed corporis sit explicabo ut est. Et est placeat ea sunt sunt consectetur sunt incidunt. Explicabo vel esse blanditiis dolorem culpa non quia.
```
> The prefix "4" indicates that Waldo is on the 4th line of the file:
`./serial-numbers/eaque_molestiae.txt`

### Pipes and Connecting Commands

* Sometimes it's useful to output the results of a command to a text file for further analysis, reference, or processing. Try running `ls > files.txt`. Notice that the file `files.txt` was created. View that file using `more`. *What do you see in the `files.txt` file?*

> The `new files.txt` contains the output of the ls command... 
> It essentially ran the `'ls'` cmd in my current directory, then print output to `> files.txt`.

* Notice that if you run `ls -alh` in the `challenge_files` directory, the files scroll by very quickly. Sometimes it would be better to get the results in a paginated format. Try running `ls -alh | more`. *Describe what you see when you run `ls -alh | more`.*

> The results are, indeed, "paginated". It's now much easier to page up/down and scroll through the files.

* Earlier, when you viewed the list of active processes on your devbox using `ps aux`, the list was probably really long. You can make this list more manageable by using the pipe (`|`) to filter the results of `ps` using `grep`. Run `ps aux | grep <your_username>` to see what processes are running for your specific user. *Paste the list of processes that reference your username here:*

> Evidently, there are a lot of background processes running on my machine!!!

```Shell
Bryans-MacBook-Air:wats1030-intro-to-unix bryan$ ps aux | grep bryan
bryan              666  14.2  0.7  3551676  62684   ??  S    24Sep17 238:14.98 /Library/Application Support/Adobe/Adobe Desktop Common/HEX/Adobe CEF Helper.app/Contents/MacOS/Adobe CEF Helper --type=renderer --disable-pinch --disable-databases --primordial-pipe-token=83634D9413FA008C55A2CA32D3CF6804 --lang=en-US --lang=en-US --log-file=/Users/bryan/Library/Logs/CreativeCloud/ACC/CEF.log --log-severity=warning --user-agent=Mozilla/5.0 (Macintosh) AppleWebKit/537.36 (KHTML, like Gecko) Safari/537.36 CreativeCloud/4.2.0.211 --num-raster-threads=2 --enable-gpu-rasterization --enable-zero-copy --enable-gpu-memory-buffer-compositor-resources --enable-main-frame-before-activation --content-image-texture-target=0,0,3553;0,1,3553;0,2,3553;0,3,3553;0,4,3553;0,5,3553;0,6,3553;0,7,3553;0,8,3553;0,9,3553;0,10,34037;0,11,34037;0,12,34037;0,13,3553;0,14,3553;0,15,3553;1,0,3553;1,1,3553;1,2,3553;1,3,3553;1,4,3553;1,5,3553;1,6,3553;1,7,3553;1,8,3553;1,9,3553;1,10,34037;1,11,34037;1,12,34037;1,13,3553;1,14,3553;1,15,3553;2,0,3553;2,1,3553;2,2,3553;2,3,3553;2,4,3553;2,5,34037;2,6,3553;2,7,3553;2,8,3553;2,9,3553;2,10,3553;2,11,3553;2,12,34037;2,13,3553;2,14,34037;2,15,34037;3,0,3553;3,1,3553;3,2,3553;3,3,3553;3,4,3553;3,5,34037;3,6,3553;3,7,3553;3,8,3553;3,9,3553;3,10,3553;3,11,3553;3,12,34037;3,13,3553;3,14,34037;3,15,34037 --service-request-channel-token=83634D9413FA008C55A2CA32D3CF6804 --renderer-client-id=3
bryan              454   6.6  0.3  2960908  21476   ??  S    24Sep17 111:55.39 /Applications/Utilities/Adobe Creative Cloud/ACC/Creative Cloud.app/Contents/MacOS/Creative Cloud --showwindow=false --onOSstartup=true
bryan             6828   6.3  0.3  2760980  26736   ??  S    Fri07AM  55:17.63 /Library/Application Support/Adobe/Adobe Desktop Common/HEX/Adobe CEF Helper.app/Contents/MacOS/Adobe CEF Helper --type=gpu-process --lang=en-US --log-file=/Users/bryan/Library/Logs/CreativeCloud/ACC/CEF.log --log-severity=warning --user-agent=Mozilla/5.0 (Macintosh) AppleWebKit/537.36 (KHTML, like Gecko) Safari/537.36 CreativeCloud/4.2.0.211 --supports-dual-gpus=false --gpu-driver-bug-workarounds=0,1,10,23,25,36,39,47,53,61,63,64,65,66,68,73,74,76,79,84,85,86,89,92 --disable-gl-extensions=GL_KHR_blend_equation_advanced GL_KHR_blend_equation_advanced_coherent --gpu-vendor-id=0x8086 --gpu-device-id=0x0a26 --gpu-driver-vendor --gpu-driver-version --gpu-driver-date --gpu-active-vendor-id=0x8086 --gpu-active-device-id=0x0a26 --lang=en-US --log-file=/Users/bryan/Library/Logs/CreativeCloud/ACC/CEF.log --log-severity=warning --user-agent=Mozilla/5.0 (Macintosh) AppleWebKit/537.36 (KHTML, like Gecko) Safari/537.36 CreativeCloud/4.2.0.211 --service-request-channel-token=97A21159789A003328DE3616C5CE31FC
bryan            14892   1.1  0.5  3180444  43080   ??  S     5:17PM   0:00.25 /Applications/VSCode-darwin-stable/Visual Studio Code.app/Contents/Frameworks/Code Helper.app/Contents/MacOS/Code Helper /Applications/VSCode-darwin-stable/Visual Studio Code.app/Contents/Resources/app/out/bootstrap --type=terminal
bryan            13306   0.7  2.3  4357624 195868   ??  S     8:13PM   4:36.54 /Applications/VSCode-darwin-stable/Visual Studio Code.app/Contents/Frameworks/Code Helper.app/Contents/MacOS/Code Helper --type=renderer --js-flags=--nolazy --no-sandbox --primordial-pipe-token=2D70AD756C52ECCAB652D6FC19AFDA4B --lang=en-US --app-path=/Applications/VSCode-darwin-stable/Visual Studio Code.app/Contents/Resources/app --node-integration=true --webview-tag=true --no-sandbox --background-color=#002b36 --disable-blink-features=Auxclick --enable-pinch --num-raster-threads=2 --enable-zero-copy --enable-gpu-memory-buffer-compositor-resources --enable-main-frame-before-activation --content-image-texture-target=0,0,3553;0,1,3553;0,2,3553;0,3,3553;0,4,3553;0,5,3553;0,6,3553;0,7,3553;0,8,3553;0,9,3553;0,10,34037;0,11,34037;0,12,34037;0,13,3553;0,14,3553;0,15,3553;1,0,3553;1,1,3553;1,2,3553;1,3,3553;1,4,3553;1,5,3553;1,6,3553;1,7,3553;1,8,3553;1,9,3553;1,10,34037;1,11,34037;1,12,34037;1,13,3553;1,14,3553;1,15,3553;2,0,3553;2,1,3553;2,2,3553;2,3,3553;2,4,3553;2,5,3553;2,6,3553;2,7,3553;2,8,3553;2,9,3553;2,10,34037;2,11,34037;2,12,34037;2,13,3553;2,14,3553;2,15,3553;3,0,3553;3,1,3553;3,2,3553;3,3,3553;3,4,3553;3,5,34037;3,6,3553;3,7,3553;3,8,3553;3,9,3553;3,10,3553;3,11,3553;3,12,34037;3,13,3553;3,14,34037;3,15,34037;4,0,3553;4,1,3553;4,2,3553;4,3,3553;4,4,3553;4,5,34037;4,6,3553;4,7,3553;4,8,3553;4,9,3553;4,10,3553;4,11,3553;4,12,34037;4,13,3553;4,14,34037;4,15,34037 --service-request-channel-token=2D70AD756C52ECCAB652D6FC19AFDA4B --renderer-client-id=4
bryan            13304   0.3  1.8  3625136 153736   ??  S     8:13PM   2:35.74 /Applications/VSCode-darwin-stable/Visual Studio Code.app/Contents/MacOS/Electron
bryan            13305   0.1  0.7  2884536  60620   ??  S     8:13PM   1:36.31 /Applications/VSCode-darwin-stable/Visual Studio Code.app/Contents/Frameworks/Code Helper.app/Contents/MacOS/Code Helper --type=gpu-process --no-sandbox --supports-dual-gpus=false --gpu-driver-bug-workarounds=0,1,10,23,25,36,39,47,53,61,63,64,65,66,68,73,74,76,79,84,85,86,89,92 --disable-gl-extensions=GL_KHR_blend_equation_advanced GL_KHR_blend_equation_advanced_coherent --gpu-vendor-id=0x8086 --gpu-device-id=0x0a26 --gpu-driver-vendor --gpu-driver-version --gpu-driver-date --gpu-active-vendor-id=0x8086 --gpu-active-device-id=0x0a26 --service-request-channel-token=21935DEDBE0DEE9932FCFBFB3C0907D1
bryan             6561   0.1  0.8  4469276  64016   ??  S    Thu06PM   8:55.33 /Applications/Dropbox.app/Contents/MacOS/Dropbox /firstrunupdate 359
bryan            14437   0.0  0.1  2496536  10692   ??  S<    4:46PM   0:00.04 /Applications/VSCode-darwin-stable/Visual Studio Code.app/Contents/Frameworks/Squirrel.framework/Resources/ShipIt com.microsoft.VSCode.ShipIt
bryan            14243   0.0  0.2  2499980  19612   ??  Ss    4:36PM   0:00.10 /Library/Frameworks/iTunesLibrary.framework/Versions/A/XPCServices/com.apple.iTunesLibraryService.xpc/Contents/MacOS/com.apple.iTunesLibraryService
bryan            14212   0.0  0.2  2497408  17176   ??  S     4:36PM   0:00.13 /System/Library/PrivateFrameworks/AssetCacheServices.framework/XPCServices/AssetCacheLocatorService.xpc/Contents/MacOS/AssetCacheLocatorService -a
bryan            14149   0.0  0.1 556603704   6028   ??  S     4:36PM   0:00.02 /Applications/Freedom.app/Contents/MacOS/FreedomProxy -mixpanel-token c361f25b17135001126a1ef612221a2d -port 7769 -rpcport 7770 -user-id 449824 -device-id 448939 -account-type trial
bryan            14055   0.0  0.0  2469964    948   ??  S    10:23PM   0:00.02 /System/Library/PrivateFrameworks/ToneLibrary.framework/Versions/A/XPCServices/com.apple.tonelibraryd.xpc/Contents/MacOS/com.apple.tonelibraryd
bryan            13948   0.0  0.1  2498604   8872   ??  S     9:26PM   0:00.39 /usr/libexec/fmfd
bryan            13866   0.0  0.0  2496148   3668   ??  S     9:04PM   0:00.11 /System/Library/PrivateFrameworks/CoreSpotlight.framework/Support/com.apple.spotlight.IndexAgent
bryan            13773   0.0  0.0  2461044    820 s000  Ss+   8:32PM   0:00.17 /bin/bash -l
bryan            13772   0.0  0.3  3219728  21952   ??  S     8:32PM   0:09.41 /Applications/VSCode-darwin-stable/Visual Studio Code.app/Contents/Frameworks/Code Helper.app/Contents/MacOS/Code Helper /Applications/VSCode-darwin-stable/Visual Studio Code.app/Contents/Resources/app/out/bootstrap --type=terminal
bryan            13573   0.0  0.0  2495064    988   ??  S     8:20PM   0:00.03 /System/Library/PrivateFrameworks/HelpData.framework/Versions/A/Resources/helpd
bryan            13448   0.0  0.5  2528856  40684   ??  S     8:13PM   0:02.74 /System/Library/Frameworks/CoreServices.framework/Frameworks/Metadata.framework/Versions/A/Support/mdworker -s mdworker -c MDSImporterWorker -m com.apple.mdworker.shared
bryan            13447   0.0  0.5  2535744  43616   ??  S     8:13PM   0:02.08 /System/Library/Frameworks/CoreServices.framework/Frameworks/Metadata.framework/Versions/A/Support/mdworker -s mdworker -c MDSImporterWorker -m com.apple.mdworker.shared
bryan            13446   0.0  0.6  2538184  46412   ??  S     8:13PM   0:02.26 /System/Library/Frameworks/CoreServices.framework/Frameworks/Metadata.framework/Versions/A/Support/mdworker -s mdworker -c MDSImporterWorker -m com.apple.mdworker.shared
bryan            13445   0.0  0.5  2531580  41688   ??  S     8:13PM   0:02.40 /System/Library/Frameworks/CoreServices.framework/Frameworks/Metadata.framework/Versions/A/Support/mdworker -s mdworker -c MDSImporterWorker -m com.apple.mdworker.shared
bryan            13368   0.0  0.1  3176980   5824   ??  S     8:13PM   0:00.60 /Applications/VSCode-darwin-stable/Visual Studio Code.app/Contents/Frameworks/Code Helper.app/Contents/MacOS/Code Helper /Applications/VSCode-darwin-stable/Visual Studio Code.app/Contents/Resources/app/out/bootstrap --type=searchService
bryan            13364   0.0  0.2  3183508  13556   ??  S     8:13PM   0:00.87 /Applications/VSCode-darwin-stable/Visual Studio Code.app/Contents/Frameworks/Code Helper.app/Contents/MacOS/Code Helper /Applications/VSCode-darwin-stable/Visual Studio Code.app/Contents/Resources/app/out/bootstrap --type=watcherService
bryan            13362   0.0  0.9  3267820  73288   ??  S     8:13PM   0:10.99 /Applications/VSCode-darwin-stable/Visual Studio Code.app/Contents/Frameworks/Code Helper.app/Contents/MacOS/Code Helper /Applications/VSCode-darwin-stable/Visual Studio Code.app/Contents/Resources/app/out/bootstrap --type=extensionHost
bryan            13343   0.0  0.0  2472292    972   ??  S     8:13PM   0:00.02 /Applications/VSCode-darwin-stable/Visual Studio Code.app/Contents/Frameworks/Electron Framework.framework/Resources/crashpad_handler --no-rate-limit --no-upload-gzip --database=/var/folders/pv/jgmt51n53ll_6js2g1kmqk9c0000gn/T/VSCode Crashes --metrics-dir=/var/folders/pv/jgmt51n53ll_6js2g1kmqk9c0000gn/T/VSCode Crashes --url=https://rink.hockeyapp.net/api/2/apps/21a48a66799e47fea4f52c0ff81e803d/crashes/upload --handshake-fd=61
bryan            13307   0.0  0.5  3349208  39236   ??  S     8:13PM   0:02.61 /Applications/VSCode-darwin-stable/Visual Studio Code.app/Contents/Frameworks/Code Helper.app/Contents/MacOS/Code Helper --type=renderer --js-flags=--nolazy --no-sandbox --primordial-pipe-token=B4AF9660A497B5F15F77CC1850ACF2D5 --lang=en-US --app-path=/Applications/VSCode-darwin-stable/Visual Studio Code.app/Contents/Resources/app --node-integration=true --webview-tag=true --no-sandbox --enable-pinch --num-raster-threads=2 --enable-zero-copy --enable-gpu-memory-buffer-compositor-resources --enable-main-frame-before-activation --content-image-texture-target=0,0,3553;0,1,3553;0,2,3553;0,3,3553;0,4,3553;0,5,3553;0,6,3553;0,7,3553;0,8,3553;0,9,3553;0,10,34037;0,11,34037;0,12,34037;0,13,3553;0,14,3553;0,15,3553;1,0,3553;1,1,3553;1,2,3553;1,3,3553;1,4,3553;1,5,3553;1,6,3553;1,7,3553;1,8,3553;1,9,3553;1,10,34037;1,11,34037;1,12,34037;1,13,3553;1,14,3553;1,15,3553;2,0,3553;2,1,3553;2,2,3553;2,3,3553;2,4,3553;2,5,3553;2,6,3553;2,7,3553;2,8,3553;2,9,3553;2,10,34037;2,11,34037;2,12,34037;2,13,3553;2,14,3553;2,15,3553;3,0,3553;3,1,3553;3,2,3553;3,3,3553;3,4,3553;3,5,34037;3,6,3553;3,7,3553;3,8,3553;3,9,3553;3,10,3553;3,11,3553;3,12,34037;3,13,3553;3,14,34037;3,15,34037;4,0,3553;4,1,3553;4,2,3553;4,3,3553;4,4,3553;4,5,34037;4,6,3553;4,7,3553;4,8,3553;4,9,3553;4,10,3553;4,11,3553;4,12,34037;4,13,3553;4,14,34037;4,15,34037 --service-request-channel-token=B4AF9660A497B5F15F77CC1850ACF2D5 --renderer-client-id=6
bryan            12945   0.0  0.1  2521208   5072   ??  S     7:55PM   0:00.60 /System/Library/CoreServices/CoreServicesUIAgent.app/Contents/MacOS/CoreServicesUIAgent
bryan            12868   0.0  0.0  2494760   3100   ??  S     7:53PM   0:00.05 /System/Library/PrivateFrameworks/GeoServices.framework/geodMachServiceBridge
bryan            12081   0.0  0.0  2470556    988   ??  S     6:41PM   0:00.03 /usr/libexec/spindump_agent
bryan            11906   0.0  0.0  2495740   1224   ??  S     6:18PM   0:00.05 /System/Library/PrivateFrameworks/CharacterPicker.framework/Versions/A/XPCServices/com.apple.CharacterPicker.FileService.xpc/Contents/MacOS/com.apple.CharacterPicker.FileService
bryan            11868   0.0  0.0  2470180    232   ??  S     6:13PM   0:00.04 /System/Library/PrivateFrameworks/CoreCDP.framework/Versions/A/Resources/cdpd
bryan            11866   0.0  0.0  2495272   3392   ??  S     6:13PM   0:00.16 /System/Library/PrivateFrameworks/ProtectedCloudStorage.framework/Helpers/ProtectedCloudKeySyncing
bryan            11780   0.0  0.0  2470828   1044   ??  S     6:03PM   0:00.05 /System/Library/CoreServices/Software Update.app/Contents/Resources/softwareupdate_notify_agent
bryan            11763   0.0  1.6  2607416 132184   ??  S     6:03PM   0:09.32 /System/Library/PrivateFrameworks/AssistantServices.framework/assistant_service
bryan            11744   0.0  0.0  2495128   1204   ??  S     6:03PM   0:00.07 /System/Library/PrivateFrameworks/QuickLookThumbnailing.framework/Support/com.apple.quicklook.ThumbnailsAgent
bryan            11735   0.0  0.0  2499980   2556   ??  Ss    6:03PM   0:00.17 /Library/Frameworks/iTunesLibrary.framework/Versions/A/XPCServices/com.apple.iTunesLibraryService.xpc/Contents/MacOS/com.apple.iTunesLibraryService
bryan            11733   0.0  0.1  2496640   5924   ??  S     6:03PM   0:00.18 /System/Library/CoreServices/ScopedBookmarkAgent
bryan            11708   0.0  0.0  2623856   2020   ??  Ss    6:03PM   0:32.20 /System/Library/PrivateFrameworks/AssistantServices.framework/Versions/A/XPCServices/media-indexer.xpc/Contents/MacOS/media-indexer
bryan            11706   0.0  0.1  2498260   6172   ??  S     6:03PM   0:00.32 /System/Library/CoreServices/mapspushd
bryan            11705   0.0  0.0  2497120   3724   ??  S     6:03PM   0:00.30 /System/Library/PrivateFrameworks/CacheDelete.framework/deleted
bryan            11645   0.0  0.1  2588820   7652   ??  S     5:56PM   0:05.97 /System/Library/CoreServices/SafariSupport.bundle/Contents/MacOS/SafariBookmarksSyncAgent
bryan            11597   0.0  0.3  2517256  22848   ??  S     5:55PM   0:00.37 /System/Library/CoreServices/iconservicesagent
bryan            11595   0.0  0.1  2495512   8904   ??  S     5:55PM   0:00.57 /usr/libexec/videosubscriptionsd
bryan            11594   0.0  0.1  2497392   4672   ??  S     5:55PM   0:00.13 /usr/libexec/swcd
bryan            11590   0.0  0.1  2495680   6044   ??  S     5:55PM   0:00.23 /System/Library/CoreServices/pbs
bryan            11586   0.0  0.0  2470484   1024   ??  S     5:54PM   0:00.07 /System/Library/PrivateFrameworks/StorageManagement.framework/Resources/diskspaced
bryan            11566   0.0  0.0  2461704    712   ??  Ss   Mon07AM   0:00.03 /System/Library/Frameworks/AudioToolbox.framework/XPCServices/com.apple.audio.SandboxHelper.xpc/Contents/MacOS/com.apple.audio.SandboxHelper
bryan            11564   0.0  0.1  2497584   7676   ??  S    Mon07AM   0:00.64 /System/Library/PrivateFrameworks/CloudServices.framework/Versions/A/XPCServices/com.apple.sbd.xpc/Contents/MacOS/com.apple.sbd
bryan            11563   0.0  0.0  2469692   2588   ??  S    Mon07AM   0:00.09 /System/Library/CoreServices/EscrowSecurityAlert.app/Contents/MacOS/EscrowSecurityAlert
bryan            11529   0.0  0.1  2499980   6208   ??  Ss   Mon07AM   0:00.39 /Library/Frameworks/iTunesLibrary.framework/Versions/A/XPCServices/com.apple.iTunesLibraryService.xpc/Contents/MacOS/com.apple.iTunesLibraryService
bryan            11526   0.0  0.1  2500472   6708   ??  S    Mon07AM   0:00.22 /System/Library/PrivateFrameworks/CallHistory.framework/Support/CallHistoryPluginHelper
bryan            11523   0.0  0.0  2494944   3480   ??  S    Mon07AM   0:00.07 /System/Library/PrivateFrameworks/CommunicationsFilter.framework/CMFSyncAgent.app/Contents/MacOS/CMFSyncAgent
bryan            11521   0.0  0.1  2587148   4496   ??  S    Mon07AM   0:00.41 /usr/libexec/SafariNotificationAgent
bryan            11503   0.0  0.2  2507080  13776   ??  S    Mon07AM   0:01.05 /System/Library/PrivateFrameworks/CallHistory.framework/Support/CallHistorySyncHelper
bryan            11472   0.0  1.3  3714740 113196   ??  S    Mon07AM   0:16.02 /System/Library/PrivateFrameworks/AssistantServices.framework/assistantd
bryan            11347   0.0  0.0  2469976    924   ??  S    Mon12AM   0:00.05 /System/Library/Frameworks/MediaAccessibility.framework/Versions/A/XPCServices/com.apple.accessibility.mediaaccessibilityd.xpc/Contents/MacOS/com.apple.accessibility.mediaaccessibilityd
bryan            11336   0.0  0.0  2500408   3564   ??  S    Mon12AM   0:00.38 /System/Library/CoreServices/AppleIDAuthAgent
bryan            11335   0.0  0.0  2498440   2820   ??  S    Mon12AM   0:00.85 /usr/libexec/WiFiVelocityAgent
bryan            11328   0.0  0.3  2515308  21600   ??  S    Mon12AM   0:08.50 /System/Library/PrivateFrameworks/TelephonyUtilities.framework/callservicesd
bryan            11318   0.0  0.0  2471392    896   ??  S    Mon12AM   0:00.04 /System/Library/Frameworks/CryptoTokenKit.framework/ctkd -tw
bryan            11317   0.0  0.0  2469724   1652   ??  S    Mon12AM   0:00.03 /System/Library/Frameworks/CryptoTokenKit.framework/ctkahp.bundle/Contents/MacOS/ctkahp
bryan            11315   0.0  0.0  2469836   3000   ??  S    Mon12AM   0:00.06 /System/Library/PrivateFrameworks/CoreFollowUp.framework/Versions/A/Support/followupd
bryan            11313   0.0  0.1  2470724   5036   ??  S    Mon12AM   0:00.14 /System/Library/Frameworks/Security.framework/Versions/A/Resources/CloudKeychainProxy.bundle/Contents/MacOS/CloudKeychainProxy
bryan            11312   0.0  0.1  2495136   5304   ??  S    Mon12AM   0:00.15 /System/Library/Frameworks/Security.framework/Versions/A/Resources/KeychainSyncingOverIDSProxy.bundle/Contents/MacOS/KeychainSyncingOverIDSProxy
bryan            11162   0.0  0.1  3548716   6300   ??  S    Sun10PM   0:00.20 /System/Library/PrivateFrameworks/CoreSuggestions.framework/Versions/A/Support/reversetemplated
bryan            11159   0.0  0.1  2496248   9484   ??  S    Sun10PM   0:00.36 /System/Library/PrivateFrameworks/CoreRecents.framework/Versions/A/Support/recentsd
bryan            11147   0.0  0.4  2550016  31492   ??  S    Sun10PM   0:02.46 /System/Library/PrivateFrameworks/IMDPersistence.framework/XPCServices/IMDPersistenceAgent.xpc/Contents/MacOS/IMDPersistenceAgent
bryan            11024   0.0  0.0  2498500   2976   ??  S    Sun09PM   0:00.24 /usr/libexec/networkserviceproxy
bryan            11019   0.0  0.1  2558492   5068   ??  S    Sun09PM   0:01.86 /System/Library/CoreServices/OSDUIHelper.app/Contents/MacOS/OSDUIHelper
bryan            11004   0.0  0.2  2508524  20156   ??  S    Sun09PM   0:02.82 /System/Library/PrivateFrameworks/GeoServices.framework/Versions/A/XPCServices/com.apple.geod.xpc/Contents/MacOS/com.apple.geod
bryan            11000   0.0  0.2  2507864  20960   ??  S    Sun09PM   0:05.75 /System/Library/PrivateFrameworks/CloudKitDaemon.framework/Support/cloudd
bryan            10999   0.0  0.1  2502176   8980   ??  S    Sun09PM   0:00.47 /usr/libexec/keyboardservicesd
bryan            10998   0.0  0.0  2469632   2516   ??  S    Sun09PM   0:00.15 /System/Library/Frameworks/ApplicationServices.framework/Versions/A/Frameworks/HIServices.framework/Versions/A/XPCServices/com.apple.hiservices-xpcservice.xpc/Contents/MacOS/com.apple.hiservices-xpcservice
bryan            10985   0.0  0.1  2469676   6348   ??  S    Sun09PM   0:00.80 /System/Library/Frameworks/AddressBook.framework/Executables/ContactsAccountsService
bryan            10984   0.0  0.1  2497092   7372   ??  S    Sun09PM   0:00.68 /usr/libexec/secinitd
bryan            10983   0.0  0.3  2529824  24412   ??  S    Sun09PM   0:08.97 /System/Library/PrivateFrameworks/MessagesKit.framework/Resources/soagent.app/Contents/MacOS/soagent
bryan             9449   0.0  0.1  2495648  10820   ??  S    Sun09AM   0:06.15 /System/Library/PrivateFrameworks/ViewBridge.framework/Versions/A/XPCServices/ViewBridgeAuxiliary.xpc/Contents/MacOS/ViewBridgeAuxiliary
bryan             9234   0.0  0.0   475516    208   ??  S    Sun09AM   0:21.41 /Library/DropboxHelperTools/Dropbox_u501/dbfseventsd
bryan             8528   0.0  0.0  2518812   1332   ??  Ss   Sat01PM   0:20.57 /System/Library/PrivateFrameworks/DiskImages.framework/Resources/diskimages-helper -uuid817F7438-5500-4C4B-9DB3-143F6D4432D9 -post-exec 4
bryan             8498   0.0  0.0  2518180   1388   ??  Ss   Sat01PM   0:24.44 /System/Library/PrivateFrameworks/DiskImages.framework/Resources/diskimages-helper -uuidF76EC61A-66E7-4093-9854-DED8334E9B17 -post-exec 4
bryan             8269   0.0  0.0  2517852   2568   ??  S    Sat11AM   0:04.45 /System/Library/CoreServices/rcd.app/Contents/MacOS/rcd
bryan             7033   0.0  0.0  2470168   1788   ??  S    Fri08AM   0:00.15 /System/Library/PrivateFrameworks/CloudFamilyRestrictions.framework/cloudfamilyrestrictionsd
bryan             7031   0.0  0.0  2496836   1016   ??  S    Fri08AM   0:00.14 /System/Library/PrivateFrameworks/FamilyCircle.framework/Versions/A/Resources/familycircled
bryan             6659   0.0  0.0  2521656   3908   ??  S    Thu06PM   0:05.95 /System/Library/PrivateFrameworks/CommerceKit.framework/Versions/A/Resources/storeuid.app/Contents/MacOS/storeuid
bryan             6606   0.0  0.1  2555708   4376   ??  Ss   Thu06PM   0:06.15 /Applications/Dropbox.app/Contents/PlugIns/garcon.appex/Contents/MacOS/garcon
bryan             6587   0.0  0.1  2522180  12036   ??  Ss   Thu06PM   0:06.42 /Applications/Dropbox.app/Contents/XPCServices/DropboxActivityProvider.xpc/Contents/MacOS/DropboxActivityProvider
bryan             6562   0.0  0.0  2497444    376   ??  S    Thu06PM   0:00.06 /Applications/Dropbox.app/Contents/MacOS/Dropbox -type:exit-monitor -method:collectupload -session-token:3247f258-ce14-4a64-8a0e-89823b00904b -target-handle:6561 -target-shutdown-event:4 -target-command-line:/Applications/Dropbox.app/Contents/MacOS/Dropbox/firstrunupdate 359
bryan             6700   0.0  0.0  2498916   2744   ??  S    28Sep17   0:00.88 /usr/libexec/avconferenced
bryan             6450   0.0  0.2  2489088  15480   ??  S    28Sep17   0:26.01 /usr/sbin/cfprefsd agent
bryan             3097   0.0  0.0  2470044    876   ??  S    26Sep17   0:00.14 /System/Library/PrivateFrameworks/KerberosHelper/Helpers/DiskUnmountWatcher
bryan             2523   0.0  0.0  2497416    968   ??  S    25Sep17   0:01.61 /System/Library/PrivateFrameworks/CommerceKit.framework/Versions/A/Resources/storeinappd
bryan             1340   0.0  0.4  2733156  31840   ??  S    24Sep17   0:09.16 /System/Library/Services/AppleSpell.service/Contents/MacOS/AppleSpell
bryan             1259   0.0  0.0  2524180   1980   ??  S    24Sep17   0:01.16 /System/Library/PrivateFrameworks/BookKit.framework/Versions/A/XPCServices/com.apple.BKAgentService.xpc/Contents/MacOS/com.apple.BKAgentService
bryan             1247   0.0  0.1  2507076   7172   ??  S    24Sep17   0:01.75 /System/Library/Frameworks/ApplicationServices.framework/Frameworks/SpeechSynthesis.framework/Resources/com.apple.speech.speechsynthesisd
bryan              813   0.0  0.0  2497124    896   ??  S    24Sep17   0:02.18 /System/Library/Frameworks/CoreServices.framework/Frameworks/Metadata.framework/Versions/A/Support/mdworker -s mdworker-sizing -c MDSSizingWorker -m com.apple.mdworker.sizing
bryan              807   0.0  0.2  2622452  19380   ??  S    24Sep17  13:07.68 /System/Library/PrivateFrameworks/PhotoAnalysis.framework/Versions/A/Support/photoanalysisd
bryan              781   0.0  0.0  2454476    188   ??  S    24Sep17   0:02.37 /System/Library/Frameworks/CoreServices.framework/Frameworks/Metadata.framework/Versions/A/Support/mdflagwriter
bryan              779   0.0  0.1  2499060   8636   ??  Ss   24Sep17   0:02.87 /System/Library/PrivateFrameworks/IMFoundation.framework/XPCServices/IMRemoteURLConnectionAgent.xpc/Contents/MacOS/IMRemoteURLConnectionAgent
bryan              767   0.0  0.1  2495920   4632   ??  S    24Sep17   0:02.50 /System/Library/Frameworks/CoreServices.framework/Frameworks/Metadata.framework/Versions/A/Support/mdwrite
bryan              728   0.0  0.6  2632456  47800   ??  S    24Sep17   0:57.37 /System/Library/PrivateFrameworks/CoreSuggestions.framework/Versions/A/Support/suggestd
bryan              669   0.0  0.0  2471068   1096   ??  S    24Sep17   0:00.18 /usr/libexec/USBAgent
bryan              668   0.0  0.0  2469660   3300   ??  S    24Sep17   5:30.48 /Library/Application Support/Adobe/Adobe Desktop Common/ADS/Adobe Desktop Service.app/Contents/Frameworks/AdobeCrashReporter.framework/Versions/A/AdobeCRDaemon.app/Contents/MacOS/AdobeCRDaemon 665 Adobe Desktop Service 4.2 /Library/Application Support/Adobe/Adobe Desktop Common/ADS/Adobe Desktop Service.app/Contents/Resources/AdobeDesktopService.icns /Library/Application Support/Adobe/Adobe Desktop Common/ADS/Adobe Desktop Service.app/Contents/Frameworks/AdobeCrashReporter.framework/Versions/A/Adobe Crash Reporter.app/Contents/MacOS/Adobe Crash Reporter 1
bryan              665   0.0  0.1   867760  12576   ??  S    24Sep17   3:25.09 /Library/Application Support/Adobe/Adobe Desktop Common/ADS/Adobe Desktop Service.app/Contents/MacOS/Adobe Desktop Service --onOSstartup=true --showwindow=false --waitForRegistration=true
bryan              660   0.0  0.1  2521728   5328   ??  S    24Sep17   0:13.70 /System/Library/PrivateFrameworks/CommerceKit.framework/Resources/LaterAgent.app/Contents/MacOS/LaterAgent
bryan              611   0.0  0.0  2469448   1756   ??  S    24Sep17   0:00.38 /System/Library/PrivateFrameworks/MediaRemote.framework/Support/mediaremoteagent
bryan              606   0.0  0.1  2542812   5748   ??  Ss   24Sep17   0:41.60 /System/Library/PrivateFrameworks/PhotoLibraryPrivate.framework/Versions/A/Frameworks/PhotoLibraryServices.framework/Versions/A/XPCServices/com.apple.photomoments.xpc/Contents/MacOS/com.apple.photomoments
bryan              602   0.0  0.0  2469660   3348   ??  S    24Sep17   5:10.02 /Applications/Utilities/Adobe Creative Cloud/ACC/Creative Cloud.app/Contents/Frameworks/AdobeCrashReporter.framework/Versions/A/AdobeCRDaemon.app/Contents/MacOS/AdobeCRDaemon 454 Creative Cloud 4.2 /Applications/Utilities/Adobe Creative Cloud/ACC/Creative Cloud.app/Contents/Resources/CreativeCloud.icns /Applications/Utilities/Adobe Creative Cloud/ACC/Creative Cloud.app/Contents/Frameworks/AdobeCrashReporter.framework/Versions/A/Adobe Crash Reporter.app/Contents/MacOS/Adobe Crash Reporter 1
bryan              599   0.0  0.0   692924   1816   ??  S    24Sep17   1:03.45 /Applications/Utilities/Adobe Application Manager/IPC/AdobeIPCBroker.app/Contents/MacOS/AdobeIPCBroker -launchedbyvulcan /Applications/Utilities/Adobe Creative Cloud/ACC/Creative Cloud.app/Contents/MacOS/Creative Cloud
bryan              586   0.0  0.3  2545016  22956   ??  Ss   24Sep17   0:10.90 /System/Library/Input Methods/PressAndHold.app/Contents/PlugIns/PAH_Extension.appex/Contents/MacOS/PAH_Extension
bryan              546   0.0  0.1  2528304   5948   ??  Ss   24Sep17   0:04.84 /System/Library/PrivateFrameworks/CommerceKit.framework/Versions/A/XPCServices/com.apple.CommerceKit.TransactionService.xpc/Contents/MacOS/com.apple.CommerceKit.TransactionService
bryan              537   0.0  0.1  2495888   6124   ??  Ss   24Sep17   0:05.67 /System/Library/PrivateFrameworks/CoreWLANKit.framework/Versions/A/XPCServices/WiFiProxy.xpc/Contents/MacOS/WiFiProxy
bryan              533   0.0  0.0  2528408   1244   ??  S    24Sep17   7:14.21 /System/Library/PrivateFrameworks/PhotoLibraryPrivate.framework/Versions/A/Support/photolibraryd
bryan              532   0.0  0.0  2496176    992   ??  S    24Sep17   0:00.19 /System/Library/PrivateFrameworks/CommerceKit.framework/Versions/A/Resources/storelegacy
bryan              479   0.0  0.1  2528316   5704   ??  Ss   24Sep17   0:16.18 /Applications/OneDrive.app/Contents/PlugIns/FinderSync.appex/Contents/MacOS/FinderSync
bryan              460   0.0  0.1  2553624  10328   ??  S    24Sep17   0:17.68 com.gopro.GoPro-Studio-GoPro-Importer
bryan              458   0.0  0.1  2496300   7064   ??  S    24Sep17   0:06.31 /System/Library/CoreServices/diagnostics_agent
bryan              457   0.0  0.1  2521264   8428   ??  S    24Sep17   0:15.71 /System/Library/CoreServices/WiFiAgent.app/Contents/MacOS/WiFiAgent
bryan              455   0.0  0.1  2528476   7620   ??  S    24Sep17   0:16.11 /System/Library/PrivateFrameworks/Noticeboard.framework/Versions/A/Resources/nbagent.app/Contents/MacOS/nbagent
bryan              453   0.0  0.1  2496356   4664   ??  S    24Sep17   0:01.29 /System/Library/CoreServices/cloudpaird
bryan              451   0.0  0.1  2517436   4956   ??  S    24Sep17   0:18.04 /System/Library/CoreServices/AirPlayUIAgent.app/Contents/MacOS/AirPlayUIAgent --launchd
bryan              450   0.0  0.0  2472852   1788   ??  S    24Sep17   0:13.00 /Users/bryan/Library/Application Support/Spotify/SpotifyWebHelper
bryan              447   0.0  0.1  2499324   5716   ??  S    24Sep17   0:01.91 /System/Library/Image Capture/Support/icdd
bryan              445   0.0  0.1  2521900   5228   ??  S    24Sep17   0:24.77 /System/Library/CoreServices/Siri.app/Contents/MacOS/Siri launchd
bryan              444   0.0  0.1  2516360   7108   ??  S    24Sep17   0:11.98 /System/Library/Frameworks/InputMethodKit.framework/Resources/imklaunchagent
bryan              443   0.0  0.5  2774884  42892   ??  S    24Sep17   1:22.48 /System/Library/CoreServices/NotificationCenter.app/Contents/MacOS/NotificationCenter
bryan              436   0.0  0.1  2517328   4260   ??  S    24Sep17   0:13.92 /System/Library/CoreServices/FolderActionsDispatcher.app/Contents/MacOS/FolderActionsDispatcher
bryan              425   0.0  0.3  2535804  22192   ??  S    24Sep17   0:42.27 /System/Library/PrivateFrameworks/CommerceKit.framework/Versions/A/Resources/storeassetd
bryan              415   0.0  0.2  2504184  14656   ??  S    24Sep17   0:08.72 /usr/libexec/nsurlsessiond
bryan              409   0.0  0.2  2504780  18100   ??  S    24Sep17   0:09.31 /System/Library/PrivateFrameworks/CommerceKit.framework/Versions/A/Resources/storeaccountd
bryan              406   0.0  0.0  2536136   4088   ??  Ss   24Sep17   0:13.48 /Applications/Utilities/Adobe Sync/CoreSync/Core Sync.app/Contents/PlugIns/ACCFinderSync.appex/Contents/MacOS/ACCFinderSync
bryan              401   0.0  0.1  2521144   9612   ??  S    24Sep17   0:06.52 /System/Library/PrivateFrameworks/CoreParsec.framework/parsecd
bryan              393   0.0  0.3  2676460  23196   ??  S    24Sep17   0:22.07 /System/Library/CoreServices/Spotlight.app/Contents/MacOS/Spotlight
bryan              389   0.0  0.1  2501620   6508   ??  S    24Sep17   0:04.67 /System/Library/PrivateFrameworks/PassKitCore.framework/passd
bryan              386   0.0  0.0  2495092   1744   ??  S    24Sep17   0:00.51 /System/Library/PrivateFrameworks/AskPermission.framework/Versions/A/Resources/askpermissiond
bryan              385   0.0  0.2  2508500  13596   ??  S    24Sep17   0:09.07 /System/Library/PrivateFrameworks/GameCenterFoundation.framework/Versions/A/gamed
bryan              383   0.0  0.2  2504756  19904   ??  S    24Sep17   0:32.70 /System/Library/PrivateFrameworks/AuthKit.framework/Versions/A/Support/akd
bryan              370   0.0  0.2  2511076  19208   ??  Ss   24Sep17   0:20.80 /System/Library/PrivateFrameworks/CalendarNotification.framework/Versions/A/XPCServices/CalNCService.xpc/Contents/MacOS/CalNCService
bryan              368   0.0  0.0  2495072   3684   ??  S    24Sep17   0:00.83 /System/Library/CoreServices/SocialPushAgent.app/Contents/MacOS/SocialPushAgent
bryan              365   0.0  0.1  2498440   4740   ??  S    24Sep17   0:01.23 /System/Library/PrivateFrameworks/CloudPhotoServices.framework/Versions/A/Frameworks/CloudPhotosConfigurationXPC.framework/Versions/A/XPCServices/com.apple.CloudPhotosConfiguration.xpc/Contents/MacOS/com.apple.CloudPhotosConfiguration
bryan              363   0.0  0.3  3712420  27376   ??  S    24Sep17   7:09.44 /Applications/Freedom.app/Contents/MacOS/Freedom
bryan              361   0.0  0.5  2946256  44424   ??  S    24Sep17   4:12.72 /Applications/OneDrive.app/Contents/MacOS/OneDrive
bryan              358   0.0  0.5  2532748  44860   ??  S    24Sep17   2:14.91 /System/Library/PrivateFrameworks/CalendarAgent.framework/Executables/CalendarAgent
bryan              354   0.0  0.0  2496560   1968   ??  S    24Sep17   0:11.38 /Applications/iTunes.app/Contents/MacOS/iTunesHelper.app/Contents/MacOS/iTunesHelper
bryan              348   0.0  0.4  2547728  30976   ??  S    24Sep17   0:57.60 /System/Library/Frameworks/Accounts.framework/Versions/A/Support/accountsd
bryan              347   0.0  0.3  2503284  22880   ??  S    24Sep17   1:10.28 /System/Library/PrivateFrameworks/SyncedDefaults.framework/Support/syncdefaultsd
bryan              345   0.0  0.1  2497808   8524   ??  S    24Sep17   0:06.04 /System/Library/PrivateFrameworks/TCC.framework/Resources/tccd
bryan              344   0.0  0.2  2511884  19396   ??  S    24Sep17   0:23.80 /System/Library/PrivateFrameworks/IMCore.framework/imagent.app/Contents/MacOS/imagent
bryan              343   0.0  0.3  2518128  24620   ??  S    24Sep17   0:39.29 /System/Library/PrivateFrameworks/IDS.framework/identityservicesd.app/Contents/MacOS/identityservicesd
bryan              342   0.0  0.2  2513812  19416   ??  S    24Sep17   0:35.80 /usr/libexec/sharingd
bryan              340   0.0  0.1  2499632  10116   ??  S    24Sep17   0:17.59 /usr/libexec/nsurlstoraged
bryan              339   0.0  0.2  2498912  12872   ??  S    24Sep17   0:21.58 /usr/sbin/usernoted
bryan              334   0.0  0.1  2522360   7792   ??  Ss   24Sep17   0:16.07 /System/Library/CoreServices/Dock.app/Contents/XPCServices/com.apple.dock.extra.xpc/Contents/MacOS/com.apple.dock.extra
bryan              331   0.0  0.1  2497180   6224   ??  S    24Sep17   0:06.88 /System/Library/PrivateFrameworks/UserActivity.framework/Agents/useractivityd
bryan              330   0.0  0.1  2497316   7944   ??  S    24Sep17   0:03.51 /System/Library/CoreServices/sharedfilelistd
bryan              320   0.0  0.0  3620024   2176   ??  S    24Sep17   0:49.25 /System/Library/PrivateFrameworks/CommerceKit.framework/Versions/A/Resources/storedownloadd
bryan              319   0.0  0.1  2545776  11416   ??  S    24Sep17   0:45.23 /System/Library/CoreServices/cloudphotosd.app/Contents/MacOS/cloudphotosd
bryan              313   0.0  0.1  2503304   9200   ??  S    24Sep17   0:19.01 /usr/libexec/pkd
bryan              312   0.0  0.2  2500460  16956   ??  S    24Sep17   0:08.98 /System/Library/PrivateFrameworks/CloudDocsDaemon.framework/Versions/A/Support/bird
bryan              308   0.0  0.1  2529320   9176   ??  S    24Sep17   0:51.80 /System/Library/Frameworks/ApplicationServices.framework/Frameworks/ATS.framework/Support/fontd
bryan              307   0.0  0.0  2487484   2512   ??  S    24Sep17   0:00.46 /usr/libexec/pboard
bryan              304   0.0  0.1  2500128  11732   ??  S    24Sep17   0:17.72 /usr/libexec/secd
bryan              303   0.0  0.1  2504256  11528   ??  S    24Sep17   0:10.73 /usr/libexec/lsd
bryan              302   0.0  0.2  2508900  15808   ??  S    24Sep17   2:39.59 /usr/libexec/trustd --agent
bryan              301   0.0  2.8  4681320 238248   ??  S    24Sep17   2:50.13 /System/Library/CoreServices/Finder.app/Contents/MacOS/Finder
bryan              300   0.0  0.4  2665444  37692   ??  S    24Sep17   1:30.01 /System/Library/CoreServices/SystemUIServer.app/Contents/MacOS/SystemUIServer
bryan              298   0.0  0.4  2767940  33556   ??  S    24Sep17   1:01.27 /System/Library/CoreServices/Dock.app/Contents/MacOS/Dock
bryan              297   0.0  0.1  2519604  10008   ??  S    24Sep17   0:30.60 /System/Library/Frameworks/CoreTelephony.framework/Support/CommCenter -L
bryan              295   0.0  0.1  2476628   5924   ??  S    24Sep17   1:00.15 /usr/sbin/distnoted agent
bryan              293   0.0  0.1  2497216   9456   ??  S    24Sep17   0:24.57 /usr/libexec/UserEventAgent (Aqua)
bryan              112   0.0  0.5  2620588  40368   ??  Ss   24Sep17   1:22.04 /System/Library/CoreServices/loginwindow.app/Contents/MacOS/loginwindow console
bryan            14930   0.0  0.0  2442020    788 s001  S+    5:18PM   0:00.00 grep bryan
bryan            14893   0.0  0.0  2452852   1468 s001  Ss    5:17PM   0:00.01 /bin/bash -l
bryan            14891   0.0  0.3  2504548  26076   ??  SN    5:17PM   0:00.69 /System/Library/Frameworks/CoreServices.framework/Frameworks/Metadata.framework/Versions/A/Support/mdworker -s mdworker-bundle -c MDSImporterBundleFinder -m com.apple.mdworker.bundles
bryan            14889   0.0  0.3  3016524  22276   ??  S     5:17PM   0:00.11 /System/Library/Frameworks/QuickLook.framework/Resources/quicklookd.app/Contents/MacOS/quicklookd
bryan            14887   0.0  0.3  2517636  27364   ??  Ss    5:17PM   0:00.20 /System/Library/Frameworks/Metal.framework/Versions/A/XPCServices/MTLCompilerService.xpc/Contents/MacOS/MTLCompilerService
bryan            14885   0.0  0.9  2613900  76436   ??  S     5:17PM   0:10.32 /Applications/Utilities/Activity Monitor.app/Contents/MacOS/Activity Monitor
Bryans-MacBook-Air:wats1030-intro-to-unix bryan$
```
