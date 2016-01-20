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

* Get an idea of where you are in the operating system. Use the `pwd` command to find your "path to working directory"--your current location in the filesystem of your devbox. */Users/Afi*
* Discover more about this filesystem. Use `ls` (the "list" command)to see what is in this directory. *Applications	Documents	Library		Music		Public
Desktop		Downloads	Movies		Pictures	Web*
* You can use *options* to modify how a command runs. Try using `ls -alh` to see the contents of your current directory.
* &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; *-l shows you the directory contents as a long list*
* &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; *-a shows files with '.' in the path*
* &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; *-h changes the format of the file size numbers*
* The `man` ("manual") command tells you more about how any given command works. (*WARNING:* CodeAnywhere does not support the man command. You can click the following link to complete this task: http://linux.die.net/man/)Run `man` to see instructions about how to use `man`. Then use `man` to learn what the `a`, `l`, and `h` options mean when used with the `ls` command.
* &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; *-l shows you the directory contents as a long list*
* &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; *-a shows files with '.' in the path*
* &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; *-h changes the format of the file size numbers*
* Commands can also take *arguments*, which are usually the names of files or locations that you want the command to work with. Try running `ls /` to see what files are in the *root* directory of the filesystem. *What files and directories do you see listed?*

Applications			bin				net
Library				cores				private
Network				dev				sbin
System				etc				tmp
Users				home				usr
Volumes				installer.failurerequests	var

* A Unix filesystem has a few special shortcuts to refer to specific locations. `/` indicates the *root* of the filesystem, meaning the top-most directory in the filesystem hierarchy. Use the `cd` ("change directory") command to move to the root directory. (Hint: Use `man` to look up the `cd` command if you have any issues) *Then run `pwd` and paste the output here:*
* Another special shortcut in Unix is the `~` location. This indicates the *user root* directory, meaning the top-most directory in the hierarchy that comes below your user account. Use `cd` to move to `~`. *Run `pwd` and paste the response here:*

/

* Change directory into the `challenge_files` directory. Use `ls` to find only the files with a `.demo` pattern. *How many files do you find?*

2015_special_stuff.demo		cloaked-wookie.demo		scooter-double-mamba.demo

* Use the `cd` command to move "up" one directory. *Where are you in the filesystem now?*

/Users/Afi/documents/github/repos/wats1030-intro-to-unix

* Press the up arrow on your keyboard. *What just happened?*

repeated the last command entered

* Press the up arrow a few more times. *What do you see?*

a history of what I've entered

* Run the `history` command. *What do you see?*

a listed history of the commands i've run

### Observing the System

* Discover what account you are logged into using the `whoami` command. *What username are you currently using?*

Afi

* Discover who else is on your system with the `who` command. *Are any other users using your system? If so, list them here:*

Afi      console  Jan 17 11:24 
Afi      ttys000  Jan 19 20:26 

* How long has your system been running? Use `uptime` to see, and *paste the result here:*

22:11  up 2 days, 10:47, 2 users, load averages: 1.11 1.20 1.21

* Run `ps aux` and review the results. (Hint: Use `man` to learn more about the `ps` command and options.) *How do you interpret what you see here?*

it looks like a list of processes currently running on my maching along with some info about them.
top
* Run `top` and review the results. (Hint: You may need to use `ctrl-c` to get out of this app.) *How do you interpret what you see here?*

seems like the stats of all of my processes and data on how my machine is currently running

### Finding and Viewing Files

* Make sure you are in the `challenge_files` directory. Use the `*` wildcard to find all the files that have the word "credit" in the filename. *How many files did you find?*

2

* Use the `more` command to view one of the `credit_cards` files you just discovered. (Hint: Type `q` to quit viewing the file. Press the `spacebar` to page down. Use your keyboard arrows to move up/down.) *What is the date in the file you have viewed?*

01-15-2015

* Use the `find` command to search for files more effectively. Search the sub-directories under `challenge_files` to find the location of the file named `modi_laboriosam.txt`. *Where is that file located?*

./tmp/modi_laboriosam.txt

* Use the `grep` command to search for text within a file. Use `grep` on all the `.user` files in `challenge_files` to find which files contain "WA" (the abbreviation for Washington state). *How many files did you find?*

Britt-Erdman.user:O'Harachester, WA 37261
Lissie-Strosin.user:Jewessfurt, WA 00816-7241

* Use the `-r` option of `grep` to *recursively* find the text "Waldo" hidden in a file somewhere under the `challenge_files` directory. *Paste the result showing the file and line where the word "Waldo" shows up.*

./serial-numbers/eaque_molestiae.txt:Ut est maiores quia autem. Nisi modi Waldo sed corporis sit explicabo ut est. Et est placeat ea sunt sunt consectetur sunt incidunt. Explicabo vel esse blanditiis dolorem culpa non quia.

### Pipes and Connecting Commands

* Sometimes it's useful to output the results of a command to a text file for further analysis, reference, or processing. Try running `ls > files.txt`. Notice that the file `files.txt` was created. View that file using `more`. *What do you see in the `files.txt` file?*

the contents of challenge_files, alphabetized

* Notice that if you run `ls -alh` in the `challenge_files` directory, the files scroll by very quickly. Sometimes it would be better to get the results in a paginated format. 
Try running `ls -alh | more`. *Describe what you see when you run `ls -alh | more`.*

a shorter list of some of the files in challenge_files

* Earlier, when you viewed the list of active processes on your devbox using `ps aux`, the list was probably really long. You can make this list more manageable by using the pipe (`|`) to filter the results of `ps` using `grep`. Run `ps aux | grep <your_username>` to see what processes are running for your specific user. *Paste the list of processes that reference your username here:*

Afi               212   3.1 13.8  4539576 1155256   ??  S    Sun11AM  63:11.16 /Applications/Firefox.app/Contents/MacOS/firefox -psn_0_32776
Afi             16330   2.8  2.0  3944096 171300   ??  S    11:00PM   0:04.38 /Applications/Xcode.app/Contents/MacOS/Xcode
Afi             14381   2.7  1.2  2744540 102216   ??  S    10:15PM   1:03.53 /Applications/Utilities/Terminal.app/Contents/MacOS/Terminal
Afi             14311   0.1  0.4  2564852  30516   ??  S    10:13PM   0:28.66 /Users/Afi/Downloads/BetterTouchTool.app/Contents/MacOS/BetterTouchTool -psn_0_962795
Afi               360   0.1  0.2  2589816  18080   ??  S    Sun11AM   0:36.41 /System/Library/CoreServices/NotificationCenter.app/Contents/MacOS/NotificationCenter
Afi             12859   0.0  0.2  2487312  20704   ??  S     8:39PM   0:01.52 /System/Library/Frameworks/CoreServices.framework/Frameworks/Metadata.framework/Versions/A/Support/mdworker -s mdworker -c MDSImporterWorker -m com.apple.mdworker.shared
Afi             12858   0.0  0.2  2482212  13652   ??  S     8:39PM   0:00.78 /System/Library/Frameworks/CoreServices.framework/Frameworks/Metadata.framework/Versions/A/Support/mdworker -s mdworker -c MDSImporterWorker -m com.apple.mdworker.shared
Afi             12807   0.0  0.1  2501692   8652   ??  S     8:39PM   0:00.89 /Applications/Xcode.app/Contents/Developer/Library/PrivateFrameworks/CoreSimulator.framework/Versions/A/XPCServices/com.apple.CoreSimulator.CoreSimulatorService.xpc/Contents/MacOS/com.apple.CoreSimulator.CoreSimulatorService
Afi             12680   0.0  0.3  2573964  21400   ??  Ss    8:38PM   0:00.47 /System/Library/Frameworks/Foundation.framework/Versions/C/XPCServices/LookupViewService.xpc/Contents/MacOS/LookupViewService
Afi             12515   0.0  0.0  2469876   2636   ??  S     8:37PM   0:00.05 /usr/bin/ssh-agent -l
Afi             10264   0.0  0.1  2530012  11036   ??  S     7:34PM   0:00.44 /usr/libexec/SafariPlugInUpdateNotifier
Afi              9403   0.0  0.1  2484648   5004   ??  S     7:08PM   0:00.03 /System/Library/PrivateFrameworks/HelpData.framework/Versions/A/Resources/helpd
Afi              8230   0.0  0.1  2472000   5564   ??  S    Mon10PM   0:00.31 /System/Library/Frameworks/CoreServices.framework/Frameworks/Metadata.framework/Versions/A/Support/mdworker -s mdworker-sizing -c MDSSizingWorker -m com.apple.mdworker.sizing
Afi              7057   0.0  0.1  2470292   5592   ??  Ss   Mon09PM   0:00.07 /System/Library/PrivateFrameworks/CommerceKit.framework/Versions/A/XPCServices/com.apple.CommerceKit.TransactionService.xpc/Contents/MacOS/com.apple.CommerceKit.TransactionService
Afi              5491   0.0  0.2  2523044  17228   ??  Ss   Mon08PM   0:00.75 /System/Library/PrivateFrameworks/CommerceKit.framework/Versions/A/XPCServices/com.apple.CommerceKit.TransactionService.xpc/Contents/MacOS/com.apple.CommerceKit.TransactionService
Afi              5274   0.0  0.1  2470292   5672   ??  Ss   Mon08PM   0:00.12 /System/Library/PrivateFrameworks/CommerceKit.framework/Versions/A/XPCServices/com.apple.CommerceKit.TransactionService.xpc/Contents/MacOS/com.apple.CommerceKit.TransactionService
Afi              4717   0.0  0.1  2470292   5628   ??  Ss   Mon07PM   0:00.04 /System/Library/PrivateFrameworks/CommerceKit.framework/Versions/A/XPCServices/com.apple.CommerceKit.TransactionService.xpc/Contents/MacOS/com.apple.CommerceKit.TransactionService
Afi              4716   0.0  0.0  2469412   2160   ??  S    Mon07PM   0:00.02 /System/Library/PrivateFrameworks/StoreXPCServices.framework/Versions/A/XPCServices/com.apple.appstore.PluginXPCService.xpc/Contents/MacOS/com.apple.appstore.PluginXPCService
Afi              4713   0.0  0.1  2542636   9776   ??  S    Mon07PM   0:00.47 /System/Library/PrivateFrameworks/CommerceKit.framework/Versions/A/Resources/storeuid.app/Contents/MacOS/storeuid
Afi              4711   0.0  1.0  3967008  83568   ??  Ss   Mon07PM   4:18.34 /System/Library/Frameworks/WebKit.framework/Versions/A/XPCServices/com.apple.WebKit.WebContent.xpc/Contents/MacOS/com.apple.WebKit.WebContent
Afi              4709   0.0  0.7  3774212  54584   ??  S    Mon07PM   0:08.84 /Applications/App Store.app/Contents/MacOS/App Store
Afi              4019   0.0  0.1  2470292   5684   ??  Ss   Mon07PM   0:00.06 /System/Library/PrivateFrameworks/CommerceKit.framework/Versions/A/XPCServices/com.apple.CommerceKit.TransactionService.xpc/Contents/MacOS/com.apple.CommerceKit.TransactionService
Afi              3904   0.0  0.2  2541772  14524   ??  S    Mon07PM   0:00.68 /System/Library/PrivateFrameworks/Noticeboard.framework/Versions/A/Resources/nbagent.app/Contents/MacOS/nbagent
Afi              3281   0.0  0.2  2544540  13944   ??  S    Mon06PM   0:00.58 /System/Library/CoreServices/LocationMenu.app/Contents/MacOS/LocationMenu
Afi              2097   0.0  0.0  2542676   3024   ??  S    Mon08AM   0:00.54 /System/Library/PrivateFrameworks/CloudServices.framework/Resources/EscrowSecurityAlert.app/Contents/MacOS/EscrowSecurityAlert
Afi              1128   0.0  0.0  2493764    712   ??  Ss   Sun06PM   0:00.09 /System/Library/Frameworks/AudioToolbox.framework/XPCServices/com.apple.audio.ComponentHelper.xpc/Contents/MacOS/com.apple.audio.ComponentHelper
Afi              1127   0.0  0.0  2469456    596   ??  Ss   Sun06PM   0:00.04 /System/Library/Frameworks/AudioToolbox.framework/XPCServices/com.apple.audio.SandboxHelper.xpc/Contents/MacOS/com.apple.audio.SandboxHelper
Afi               645   0.0  0.0  2531632   2312   ??  S    Sun11AM   0:00.52 /System/Library/PrivateFrameworks/MailService.framework/Versions/A/XPCServices/com.apple.MailServiceAgent.xpc/Contents/MacOS/com.apple.MailServiceAgent
Afi               535   0.0  0.0  2497632   1076   ??  S    Sun11AM   0:00.11 /System/Library/PrivateFrameworks/PhotoLibraryPrivate.framework/Versions/A/Support/photolibraryd
Afi               530   0.0  0.0  2502036   2780   ??  S    Sun11AM   0:00.47 /System/Library/PrivateFrameworks/CloudPhotoServices.framework/Versions/A/Frameworks/CloudPhotoServicesConfiguration.framework/Versions/A/XPCServices/com.apple.CloudPhotosConfiguration.xpc/Contents/MacOS/com.apple.CloudPhotosConfiguration
Afi               529   0.0  0.0  2567348   2968   ??  S    Sun11AM   0:00.94 /System/Library/CoreServices/cloudphotosd.app/Contents/MacOS/cloudphotosd
Afi               465   0.0  0.0  2469740    424   ??  S    Sun11AM   0:00.27 /System/Library/Frameworks/CoreServices.framework/Frameworks/Metadata.framework/Versions/A/Support/mdflagwriter
Afi               457   0.0  0.0  2469428    664   ??  S    Sun11AM   0:00.06 /System/Library/PrivateFrameworks/ToneLibrary.framework/Versions/A/XPCServices/com.apple.tonelibraryd.xpc/Contents/MacOS/com.apple.tonelibraryd
Afi               443   0.0  0.1  2496844   4868   ??  S    Sun11AM   0:01.26 /System/Library/PrivateFrameworks/GeoServices.framework/Versions/A/XPCServices/com.apple.geod.xpc/Contents/MacOS/com.apple.geod
Afi               429   0.0  0.0  2469000   1460   ??  S    Sun11AM   0:00.09 /System/Library/PrivateFrameworks/CommunicationsFilter.framework/CMFSyncAgent.app/Contents/MacOS/CMFSyncAgent
Afi               424   0.0  0.0  2493764    700   ??  Ss   Sun11AM   0:00.08 /System/Library/Frameworks/AudioToolbox.framework/XPCServices/com.apple.audio.ComponentHelper.xpc/Contents/MacOS/com.apple.audio.ComponentHelper
Afi               423   0.0  0.0  2469456    608   ??  Ss   Sun11AM   0:00.04 /System/Library/Frameworks/AudioToolbox.framework/XPCServices/com.apple.audio.SandboxHelper.xpc/Contents/MacOS/com.apple.audio.SandboxHelper
Afi               422   0.0  0.1  2513060   6136   ??  S    Sun11AM   0:01.50 /System/Library/Frameworks/ApplicationServices.framework/Frameworks/SpeechSynthesis.framework/Resources/com.apple.speech.speechsynthesisd
Afi               401   0.0  1.9  3775812 161412   ??  S    Sun11AM  14:57.82 /System/Library/PrivateFrameworks/CommerceKit.framework/Versions/A/Resources/storedownloadd
Afi               400   0.0  0.0  2540640   3092   ??  S    Sun11AM   0:00.50 /System/Library/PrivateFrameworks/CommerceKit.framework/Resources/LaterAgent.app/Contents/MacOS/LaterAgent
Afi               398   0.0  0.1  2501492   9224   ??  S    Sun11AM   1:28.80 /System/Library/PrivateFrameworks/CommerceKit.framework/Versions/A/Resources/storeassetd
Afi               397   0.0  0.0  2468920   1808   ??  S    Sun11AM   0:00.09 /System/Library/PrivateFrameworks/CommerceKit.framework/Versions/A/Resources/storelegacy
Afi               382   0.0  0.0  2493088   1916   ??  S    Sun11AM   0:00.20 /System/Library/Frameworks/InputMethodKit.framework/Versions/A/XPCServices/com.apple.InputMethodKit.UserDictionary.xpc/Contents/MacOS/com.apple.InputMethodKit.UserDictionary
Afi               379   0.0  0.2  2538828  16088   ??  S    Sun11AM   0:01.34 /System/Library/Services/AppleSpell.service/Contents/MacOS/AppleSpell -psn_0_159783
Afi               375   0.0  0.0  2468916    744   ??  Ss   Sun11AM   0:00.08 /System/Library/CoreServices/NotificationCenter.app/Contents/XPCServices/com.apple.notificationcenterui.WeatherSummary.xpc/Contents/MacOS/com.apple.notificationcenterui.WeatherSummary
Afi               372   0.0  0.5  2629640  40368   ??  S    Sun11AM   0:23.34 /Applications/Quicksilver.app/Contents/MacOS/Quicksilver
Afi               369   0.0  0.1  2498728   4424   ??  S    Sun11AM   0:01.74 /System/Library/CoreServices/diagnostics_agent
Afi               366   0.0  0.0  2492936   2132   ??  S    Sun11AM   0:00.68 /System/Library/CoreServices/cloudpaird
Afi               365   0.0  0.0  2471528   1036   ??  S    Sun11AM   0:01.16 /Users/Afi/Library/Application Support/Spotify/SpotifyWebHelper
Afi               364   0.0  0.1  2615004   7012   ??  S    Sun11AM   0:01.65 /System/Library/CoreServices/PowerChime.app/Contents/MacOS/PowerChime
Afi               357   0.0  0.0  2540676   2772   ??  S    Sun11AM   0:00.50 /System/Library/CoreServices/Keychain Circle Notification.app/Contents/MacOS/Keychain Circle Notification
Afi               355   0.0  0.0  2492908   1352   ??  S    Sun11AM   0:00.17 /System/Library/CoreServices/SocialPushAgent.app/Contents/MacOS/SocialPushAgent
Afi               353   0.0  0.0  2495648   1580   ??  S    Sun11AM   0:00.10 /usr/libexec/spindump_agent
Afi               351   0.0  0.1  2494564   8096   ??  S    Sun11AM   0:03.09 /System/Library/PrivateFrameworks/CoreRecents.framework/Versions/A/Support/recentsd
Afi               350   0.0  0.0  2534760   2372   ??  S    Sun11AM   0:01.05 /System/Library/CoreServices/AirPlayUIAgent.app/Contents/MacOS/AirPlayUIAgent --launchd
Afi               343   0.0  0.0  2468988    708   ??  Ss   Sun11AM   0:00.07 /System/Library/PrivateFrameworks/IMFoundation.framework/XPCServices/IMRemoteURLConnectionAgent.xpc/Contents/MacOS/IMRemoteURLConnectionAgent
Afi               341   0.0  0.0  2469332   1112   ??  S    Sun11AM   0:00.16 /usr/libexec/nsurlsessiond
Afi               338   0.0  0.0  2501708   4188   ??  S    Sun11AM   0:00.99 /System/Library/PrivateFrameworks/CloudKitDaemon.framework/Support/cloudd
Afi               336   0.0  0.0  2497940   4136   ??  S    Sun11AM   0:00.54 /System/Library/PrivateFrameworks/CloudServices.framework/Versions/A/XPCServices/com.apple.lakitu.xpc/Contents/MacOS/com.apple.lakitu
Afi               335   0.0  0.0  2495044   2192   ??  S    Sun11AM   0:00.26 /System/Library/PrivateFrameworks/CloudServices.framework/Resources/com.apple.sbd
Afi               334   0.0  0.0  2534368   3348   ??  S    Sun11AM   0:01.03 /System/Library/CoreServices/WiFiAgent.app/Contents/MacOS/WiFiAgent
Afi               303   0.0  0.0  2493264    876   ??  S    Sun11AM   0:00.12 /System/Library/PrivateFrameworks/Notes.framework/Versions/A/XPCServices/com.apple.NotesMigratorService.xpc/Contents/MacOS/com.apple.NotesMigratorService
Afi               302   0.0  0.0  2469052   1032   ??  S    Sun11AM   0:00.09 /System/Library/Frameworks/Security.framework/Versions/A/Resources/CloudKeychainProxy.bundle/Contents/MacOS/CloudKeychainProxy
Afi               293   0.0  0.0  2470556    688   ??  S    Sun11AM   0:00.03 /Applications/Atom.app/Contents/Frameworks/Electron Framework.framework/Resources/crashpad_handler --database=/tmp/Atom Crashes --url=http://54.249.141.255:1127/post --handshake-fd=51
Afi               291   0.0  0.1  2663220   4996   ??  S    Sun11AM   0:05.22 /Applications/Atom.app/Contents/Frameworks/Atom Helper.app/Contents/MacOS/Atom Helper --type=gpu-process --channel=214.0.680246543 --no-sandbox --supports-dual-gpus=false --gpu-driver-bug-workarounds=13,24,29,32,41,45,52,58 --gpu-vendor-id=0x8086 --gpu-device-id=0x161e --gpu-driver-vendor --gpu-driver-version
Afi               284   0.0  0.0  2496696   1100   ??  S    Sun11AM   0:00.33 /System/Library/PrivateFrameworks/DataDetectorsCore.framework/Versions/A/XPCServices/DataDetectorsDynamicData.xpc/Contents/MacOS/DataDetectorsDynamicData
Afi               283   0.0  0.0  2499584   3160   ??  S    Sun11AM   0:00.52 /System/Library/CoreServices/pbs
Afi               282   0.0  0.0  2493540    792   ??  S    Sun11AM   0:00.09 /System/Library/PrivateFrameworks/CharacterPicker.framework/Versions/A/XPCServices/com.apple.CharacterPicker.FileService.xpc/Contents/MacOS/com.apple.CharacterPicker.FileService
Afi               279   0.0  0.2  2509240  13528   ??  S    Sun11AM   0:03.87 /System/Library/PrivateFrameworks/ParsecUI.framework/Versions/A/Support/SpotlightNetHelper.app/Contents/MacOS/SpotlightNetHelper
Afi               278   0.0  0.0  2501612   1380   ??  S    Sun11AM   0:00.13 /System/Library/PrivateFrameworks/CallHistory.framework/Support/CallHistoryPluginHelper
Afi               274   0.0  0.0  2494900   2176   ??  Ss   Sun11AM   0:00.62 /System/Library/CoreServices/Menu Extras/AirPort.menu/Contents/XPCServices/com.apple.wifi.proxy.xpc/Contents/MacOS/com.apple.wifi.proxy
Afi               273   0.0  0.3  2610664  26516   ??  S    Sun11AM   0:04.54 /System/Library/CoreServices/Spotlight.app/Contents/MacOS/Spotlight
Afi               272   0.0  0.0  2553368   3960   ??  S    Sun11AM   0:00.67 /System/Library/CoreServices/CoreServicesUIAgent.app/Contents/MacOS/CoreServicesUIAgent
Afi               271   0.0  0.1  2551652   7096   ??  S    Sun11AM   0:01.35 /System/Library/PrivateFrameworks/InternetAccounts.framework/Versions/A/XPCServices/com.apple.internetaccounts.xpc/Contents/MacOS/com.apple.internetaccounts
Afi               270   0.0  0.0  2493840   1780   ??  S    Sun11AM   0:00.08 /System/Library/CoreServices/ScopedBookmarkAgent
Afi               269   0.0  0.0  2496732   3244   ??  S    Sun11AM   0:04.58 /System/Library/CoreServices/AppleIDAuthAgent
Afi               268   0.0  0.1  2547432   5640   ??  Ss   Sun11AM   0:00.75 /System/Library/CoreServices/Dock.app/Contents/XPCServices/com.apple.dock.extra.xpc/Contents/MacOS/com.apple.dock.extra
Afi               265   0.0  0.0  2495228   1760   ??  S    Sun11AM   0:00.25 /System/Library/CoreServices/lsuseractivityd
Afi               261   0.0  0.1  2508124   9136   ??  S    Sun11AM   0:03.00 /System/Library/PrivateFrameworks/CommerceKit.framework/Versions/A/Resources/storeaccountd
Afi               260   0.0  0.1  2514296   6812   ??  S    Sun11AM   0:01.36 /System/Library/PrivateFrameworks/TelephonyUtilities.framework/callservicesd
Afi               258   0.0  0.2  2790604  16656   ??  S    Sun11AM   0:06.65 /System/Library/CoreServices/iconservicesagent
Afi               256   0.0  0.0  2529132   3956   ??  S    Sun11AM   0:03.69 /System/Library/Frameworks/ApplicationServices.framework/Frameworks/ATS.framework/Support/fontd
Afi               255   0.0  0.1  2480708   8240   ??  S    Sun11AM   0:03.27 /usr/libexec/nsurlstoraged
Afi               252   0.0  0.1  2501216   6020   ??  Ss   Sun11AM   0:01.21 /System/Library/PrivateFrameworks/CalendarAgent.framework/Versions/A/XPCServices/CalNCService.xpc/Contents/MacOS/CalNCService
Afi               251   0.0  0.0  2499576   2612   ??  S    Sun11AM   0:00.67 /System/Library/Frameworks/Accounts.framework/Versions/A/Support/accountsd
Afi               250   0.0  0.1  2500200   7500   ??  S    Sun11AM   0:04.48 /System/Library/PrivateFrameworks/IMCore.framework/imagent.app/Contents/MacOS/imagent
Afi               248   0.0  0.0  2492964    868   ??  S    Sun11AM   0:00.10 /System/Library/PrivateFrameworks/AskPermission.framework/Versions/A/Resources/askpermissiond
Afi               246   0.0  0.0  2501632   2404   ??  S    Sun11AM   0:00.28 /System/Library/PrivateFrameworks/CallHistory.framework/Support/CallHistorySyncHelper
Afi               245   0.0  0.1  2494180   4668   ??  S    Sun11AM   0:00.94 /System/Library/CoreServices/mapspushd
Afi               244   0.0  0.1  2495500   4604   ??  S    Sun11AM   0:02.01 /usr/libexec/fmfd
Afi               243   0.0  0.0  2519032   1304   ??  U    Sun11AM   0:07.55 /usr/libexec/SafariCloudHistoryPushAgent
Afi               242   0.0  0.1  2515092   6372   ??  S    Sun11AM   0:02.90 /System/Library/PrivateFrameworks/GameCenterFoundation.framework/Versions/A/gamed
Afi               240   0.0  0.2  2528504  15120   ??  S    Sun11AM   0:11.50 /System/Library/PrivateFrameworks/CalendarAgent.framework/Executables/CalendarAgent
Afi               238   0.0  0.1  2533308   7332   ??  S    Sun11AM   0:01.57 /System/Library/PrivateFrameworks/MessagesKit.framework/Resources/soagent.app/Contents/MacOS/soagent
Afi               237   0.0  0.0  2494944   1772   ??  S    Sun11AM   0:00.63 /usr/libexec/secd
Afi               236   0.0  0.1  2507200   7556   ??  S    Sun11AM   0:04.60 /System/Library/PrivateFrameworks/IDS.framework/identityservicesd.app/Contents/MacOS/identityservicesd
Afi               235   0.0  0.1  2500456   4820   ??  S    Sun11AM   0:00.54 /System/Library/PrivateFrameworks/CloudDocsDaemon.framework/Versions/A/Support/bird
Afi               234   0.0  0.1  2497868   4344   ??  S    Sun11AM   0:00.54 /usr/libexec/pkd
Afi               233   0.0  0.1  2506380  10520   ??  S    Sun11AM   0:04.25 /System/Library/PrivateFrameworks/IMDPersistence.framework/XPCServices/IMDPersistenceAgent.xpc/Contents/MacOS/IMDPersistenceAgent
Afi               232   0.0  0.0  2499884   3788   ??  U    Sun11AM   0:00.61 /System/Library/PrivateFrameworks/TCC.framework/Resources/tccd
Afi               231   0.0  0.1  2508976   7088   ??  S    Sun11AM   0:02.12 /usr/libexec/sharingd
Afi               229   0.0  0.0  2493380   3052   ??  S    Sun11AM   0:00.86 /usr/libexec/secinitd
Afi               226   0.0  0.0  2469140    132   ??  S    Sun11AM   0:00.02 /usr/sbin/pboard
Afi               222   0.0  2.9  3238100 247140   ??  U    Sun11AM   0:52.22 /System/Library/CoreServices/Finder.app/Contents/MacOS/Finder
Afi               221   0.0  0.0  2495392   3544   ??  S    Sun11AM   0:02.05 /usr/sbin/usernoted
Afi               220   0.0  0.2  2590392  15380   ??  S    Sun11AM   0:11.27 /System/Library/CoreServices/SystemUIServer.app/Contents/MacOS/SystemUIServer
Afi               218   0.0  0.3  2658324  22052   ??  S    Sun11AM   0:09.77 /System/Library/CoreServices/Dock.app/Contents/MacOS/Dock
Afi               217   0.0  0.0   608152     12   ??  T    Sun11AM   0:00.01 /Applications/Microsoft OneNote.app/Contents/MacOS/Microsoft OneNote -psn_0_49164
Afi               216   0.0  1.3  3839772 110392   ??  S    Sun11AM   0:17.04 /Applications/GitHub Desktop.app/Contents/MacOS/GitHub Desktop -psn_0_45067
Afi               214   0.0  0.2  3379156  16256   ??  S    Sun11AM   0:08.21 /Applications/Atom.app/Contents/MacOS/Atom -psn_0_36873
Afi               207   0.0  1.1  4236704  93664   ??  S    Sun11AM   0:43.86 /Applications/Messages.app/Contents/MacOS/Messages -psn_0_20485
Afi               206   0.0  0.0  2483636   2932   ??  S    Sun11AM   0:05.73 /usr/sbin/cfprefsd agent
Afi               204   0.0  0.1  2475980   6460   ??  S    Sun11AM   0:19.69 /usr/sbin/distnoted agent
Afi               202   0.0  0.1  2501032   4292   ??  S    Sun11AM   0:03.84 /usr/libexec/UserEventAgent (Aqua)
Afi                88   0.0  0.2  2567924  13480   ??  Ss   Sun11AM   0:13.73 /System/Library/CoreServices/loginwindow.app/Contents/MacOS/loginwindow console
Afi             16373   0.0  0.0        0      0   ??  Z    11:00PM   0:00.00 (SFLSharedPrefsTo)
Afi             16379   0.0  0.0  2432772    644 s000  S+   11:00PM   0:00.00 grep Afi
Afi             16372   0.0  0.0        0      0   ??  Z    11:00PM   0:00.00 (SFLIconTool)
Afi             16349   0.0  0.0  2470776   2812   ??  Ss   11:00PM   0:00.02 /Applications/Xcode.app/Contents/SharedFrameworks/DVTSourceControl.framework/Versions/A/XPCServices/com.apple.dt.Xcode.sourcecontrol.WorkingCopyScanner.xpc/Contents/MacOS/com.apple.dt.Xcode.sourcecontrol.WorkingCopyScanner
Afi             16338   0.0  0.1  2472500   9192   ??  Ss   11:00PM   0:00.05 /Applications/Xcode.app/Contents/SharedFrameworks/DVTSourceControl.framework/Versions/A/XPCServices/com.apple.dt.Xcode.sourcecontrol.SSHHelper.xpc/Contents/MacOS/com.apple.dt.Xcode.sourcecontrol.SSHHelper
Afi             16268   0.0  0.3  2501460  24132   ??  S    10:59PM   0:00.32 /System/Library/Frameworks/OpenGL.framework/Versions/A/Libraries/CVMCompiler 2
Afi             14427   0.0  0.4  2577844  30220   ??  Ss   10:16PM   0:06.95 /System/Library/Frameworks/Foundation.framework/Versions/C/XPCServices/LookupViewService.xpc/Contents/MacOS/LookupViewService
Afi             14384   0.0  0.0  2461020   1428 s000  S    10:15PM   0:00.34 -bash
root            14383   0.0  0.0  2468972   2920 s000  Ss   10:15PM   0:00.04 login -pf Afi
Afi             14313   0.0  0.1  2533056  11040   ??  S    10:13PM   0:00.35 /Users/Afi/Downloads/BetterTouchTool.app/Contents/Resources/BTTRelaunch.app/Contents/MacOS/BTTRelaunch
Afi             12862   0.0  0.2  2484968  15332   ??  S     8:39PM   0:01.38 /System/Library/Frameworks/CoreServices.framework/Frameworks/Metadata.framework/Versions/A/Support/mdworker -s mdworker -c MDSImporterWorker -m com.apple.mdworker.shared
Afi             12860   0.0  0.2  2489964  15120   ??  S     8:39PM   0:01.08 /System/Library/Frameworks/CoreServices.framework/Frameworks/Metadata.framework/Versions/A/Support/mdworker -s mdworker -c MDSImporterWorker -m com.apple.mdworker.shared

