# Obtaining and verifying older versions of Kindle for PC/Mac software
https://www.mobileread.com/forums/showthread.php?t=283371

command:
`certutil -hashfile <filename> SHA256`

In MacOS use the command:
`shasum -a 256 <filename>`

# Summary - Amazon books published before Jan 3 2023

This is based on
```
Exactly how to remove DRM
Geremia edited this page on Jul 2, 2021 · 47 revisions
```
https://github.com/apprenticeharper/DeDRM_tools/wiki/Exactly-how-to-remove-DRM

and especially the Wiki page followed link:

`Dealing with Kindle for PC/Mac 1.19 and KFX in calibre`
https://www.mobileread.com/forums/showthread.php?t=283371

This repository not based on the following.
But future considerations are given to the following:
```
DeDRM tools for ebooks
This is a fork of Apprentice Harper's version of the DeDRM tools.
```
https://github.com/noDRM/DeDRM_tools/

The following does not affect the Appveyour build, 
because a brand new machine is created upon each build:
```
Noted, if using Kindle manually and trying to login using the 
step `Kindle ->  Tools -> Sync and Check for New Items`
and if the following error is occurring and re-occurring and re-occurring, 
`enter a valid email or mobile number`
then read the solution by the commenters _Selphira and Ozzie511
(Many times, one may have to click on `View all comments`)
```
```
delete registry key KEY_CURRENT_USER/Software/Amazon
```
https://www.reddit.com/r/Calibre/comments/hlj4z5/registering_kindle_for_pc_117/
and
https://www.reddit.com/r/Calibre/comments/hlj4z5/comment/hpf85ay/?context=3
and
https://www.reddit.com/r/Calibre/comments/hlj4z5/comment/fx0sjns/

## Critical Warning

    1. The person who is converting the book(s) from the .az3 format to the .azw format
       MUST OWN the books. This most often means PAID MONEY TO OWN THE BOOK(S).
    2. The output books producted by this build MUST BE USED as input or knowledge,
       as an `intermediate step`, to produce the `end product` open source software.
       An example may be a book on the top of "CI/CD pipelines".

## Instructions

### In the Local user desktop, Manually Go and Do

    1. Git clone this repository `azwTOazw3` to a local location
    2. If not done already, go to https://www.appveyor.com/
       and choose the button `CREATE YOUR FREE ACCOUNT NOW`
       or chooe the URL link `Sign in` as appropriate.
       BE SURE TO associate your Appveyor account with Github. 
       (I am not showing "how to associate".)
       Remember one's username: USERNAME.
    3. In Appveyor, add this repository as a Project
       https://ci.appveyor.com/projects -> (*) New Project -> 
       Github -> Select repository for your new project -> `azwTOazw3` 
    4. On one's home computer, change the directory 
       to be in the local git repository -> `cd azwTOazw3`
    5. echo #### >> README.md
    6. git commit -m "touch"
    7. git push -u origin master (or git push -u main)
    8. Find one's Amazon `logon` and `password` and have it handy
    9. Windows -> Start -> Type this -> `rdp` 
    (Appearing will be a small window called `Remote Desktop Connections`)
    10. Browse to the URL 
        (and change USERNAME to one's USERNAME): `https://ci.appveyor.com/project/USERNAME/azwtoazw3`
    11. From the blue output, and near the bottom, collect the Server (and port) and Username.
        One is looking for something like this (and your IP:Port will be different):
        ```
        Remote Desktop connection details:
          Server: 67.225.165.215:33829 (This is IP:Port)
          Username: appveyor           (This is Username)
        ```
    12. In the `Remote Desktop Connections` window.
        In `Computer` enter the `Server` IP:Port.
        In the lower left find `Show Options` and to it's right, click on the `down arrow`
    13. In `User name` enter the Username (This is often `appveyor`.) 
    14. Press the button `Connect`
    15. In the Remote Desktop Connection dialog of "Certificate errors warning" 
        press the button`Yes`.
    16. In the "Enter your credentials" small window, at the password prompt, 
        enter the password from the appveyor.yml environment section 
        variable `APPVEYOR_RDP_PASSWORD`

### In the Appveyor desktop, Manually Go and Do

(in the future I would HIGHLY prefer to use AutoIt or similar software automate SOME of this)

    1. On the Windows Desktop on the left side, click the icon "Kindle"
       or, alternately, do Windows -> Start -> (near the top) Recently Added -> Kindle
    2. Kindle -> Tools -> Options -> 
       TURN OFF: [ ] Automatically install updates when they are available without asking me.
       Press the button `Save`.
    3. Kindle -> Tools -> Sync and Check for New Items, the "Register Kindle" window appears
       Enter one's Amazon `login`.
       Enter one's Amazon `password`.
       At the bottom, press the big yellow button `Connect using Secure Server`
    4. Authentication also occur externally, e.g. a text message of verification.
       Perform that external verification.
       At the end of that verification, return here.
       Close (x" out of) that window.
       Redo Step (2).
    5. In the Kindle GUI, below the word "Library", make sure "All" is highlighted.
       In "Library All" display area, of each the book(s) of interest, 
       and one at at at time. Right click and choose `Download`.
       As each is "Right clicked Download(ed)", 
       notice the "check, in each book in the lower left corner.
       At the end of all "Right clicked Download(ed)"s 
       notice, on the left side, "Downloaded 0" changes to Downloaded #".
       (If no book(s) or one's `book(s) of interest` IS\ARE NOT SEEN,
        5.1 then, using Google Chrome, browse to the URL: https://www.amazon.com, 
        5.2 then, login with one's Amazon `login` and `password`,
        5.3 then, go to the top corner, see `Hello USERNAME Account & Lists` and click on it,
        5.4 then, hover over those words, move the mouse down to the words, 
            `Content & Devices`, then click
        5.5 then, on the new page, near the middle left side, click on the `Books` icon
        5.6 then, for EACH BOOK OF INTEREST, one at a time,
        5.7 then, in the left column, place a checkmark next to that book,
        5.8 then, in the page button bar (up near the top), 
            this button will become enabled `Deliver to Device`
        5.9 then, click `Deliver to Device`
        5.10 then, in the `Deliver to Device` click the obvious `[x] Username's Kindle for PC #`
        5.11 then, if the the solution is NOT OBVIOUS, 
             then click on ALL of the `[x] Username's Kindle for PC #`
        5.12 then, if limited by the message `Cannot select more than 6 devices`, 
             then perhaps? choose the highest PC # numbers. or
             then perhaps? remove some/all PC # numbers (because too many).
        5.13 then, (near the bottom), press the yellow button `Make Changes`
        5.14 then, on the message box `Request to deliver title(s) has been sent` 
             in the  URL _pending_request_, 
             right click and choose `Open link in new tab`
        5.15 then, manually return to the previous (pre-the-right-click) web page.
        5.16 then, close that small message box (press the `upper-right corner 'x'`)
        5.17 then, then REPEAT upon the NEXT BOOK OF INTEREST)
    6. From step 5, if one had to add book(s) to the `"Library All" display area`, 
       in the Kindle GUI of `"Library All" display area`, to its upper right and across 
       and right from the word `Library`press the `circular pointing arrows icon` 
       and this will refresh the book(s) 
    7. If not already done, In the Kindle GUI `"Library All" display area`, 
       of each the book(s) of interest, and one at at at time. 
       Right click and choose Download.
       As each is "Right clicked Download(ed)", notice the 
       "check, in each book in the lower left corner.
       At the end of all "Right clicked Download(ed)"s 
       notice, on the left side, "Downloaded 0" changes to Downloaded #".
    8. Verify, the book(s) are downloaded.
       Windows -> Start -> Command Prompt -> 
       Type this -> `dir "%HOMEDRIVE%%HOMEPATH%\Documents\My Kindle Content"`
       The number of `.azw` files seen, must(should) match the number of book(s) downloaded.
    9. Kindle -> File -> Exit
    10. On the [upper right are of the] desktop, select the icon `Delete me to continue build`.
        Right click and choose Delete. 
        !!! THIS `DELETE ICON` IS REQUIRED TO EXIT THE APPVEYOR DESKTOP !!! 
        The Appveyor build continues and finishes.

### In the Local user desktop, Manually Go and Do
     
    1. After the build is done, on one's local computer, 
       collect the artifacts (that contains the .azw3 files),
       by browsing to the URL (and change USERNAME to one's USERNAME) 
       https://ci.appveyor.com/project/USERNAME/azwtoazw3/build/artifacts
    2. Download the books.7z file artifact
    3. On that same web page, DELETE THAT artifact
    4. On the local desktop use 7-zip to extract 
       from the books.7z folders and files, the new .awz3 files
    5. Use Calibre (or other software), to read those .awz3 files


# Summary -Amazon books published since Jan 3 2023

 ```
From an error message, seen October 3, 2023, a newer 2023 book, 
REQUIRES and Amazon Kindle for PC update
when I try to read the .awz in calibre-4.23.0.msi\DeDRM_tools_6.8.1.zip 
and I am required to upgrade the NEWER KindleForPC-installer-2.0.70350.exe 
and THAT .azw file was downloaded using the NEWER KindleForPC-installer-2.0.70350.exe
(instead of the older KindleForPC-installer-1.17.44170.exe)
```

calibre-4.23.0.msi\DeDRM_tools_6.8.1.zip conversion error message:
```
This is an Amazon KFX book. It cannot be processed. 
See https://www.mobileread.com/forums/showthread.php?t=283371 
for information on how to handle KFX books. (Error Code: 1)
```


https://www.mobileread.com/forums/showthread.php?t=351285
```
Books published after January 3, 2023 
cannot be downloaded using earlier versions (1.26 and prior) of Kindle for PC.
While the newest version (1.39) of Kindle for PC will download them, 
it will be in a version of KFX that DeDRM cannot break.
Except for books only available as KFX, 
books published before January 3 are still currently able to be downloaded 
in a format that can be DeDRM'd.
Books borrowed from Kindle Unlimited can still be downloaded 
on K4PC <1.26 if it was published before January 3.

Download and Transfer

If you have an e-Ink Kindle, "Download and Transfer" is still available for purchased books, 
regardless of when they were published. 
The DRM can be removed from these files using the DeDRM plugin.
However, books borrowed from Kindle Unlimited are not eligible for Download & Transfer.

Check if the books are available on other websites that offer DRM-free 
or more easily-removed ADE (Adobe Digital Editions) DRM:

eBooks.com - https://www.ebooks.com/en-ca/
Kobo - https://www.kobo.com/
Google Play - https://play.google.com/store/books
Smashwords - https://www.smashwords.com/
Feedbooks - https://www.feedbooks.com/
Book Republic, Italian. - https://www.bookrepublic.it/
Baen, for science fiction & fantasy. - https://www.baen.com/

https://www.overdrive.com/ - allows borrowing books

many libraries offer non-resident cards
Non-Resident Library Cards
MORE
https://www.mobileread.com/forums/showthread.php?t=348192

```

https://www.mobileread.com/forums/showthread.php?t=283371
```
Important update: Amazon has made a change to their service 
so the books published since Jan 3 2023 can no longer be downloaded
 using Kindle for PC or Mac versions prior to 1.39. 
(Details in this thread.) 
This means that methods 1, 2, and 4 described below are no longer effective for those books. 
Methods 3 and 5 still work. 
There is also a new method (#6) using an old version of the Kindle for Android app described here.

Methods 3 and 5 . . .
```

Method 3 - Use an e-ink Kindle instead 
https://www.mobileread.com/forums/showthread.php?t=283371
```
BUY PHYSICAL HARDWARE: the e-ink Kindle.

Import the downloaded file into calibre using the same procedure 
that you would use for a file from Kindle for PC.

Note that Download & Transfer is not available for every book. 
Books borrowed through Kindle Unlimited or Prime Lending do not have this option. 
And there are other miscellaneous categories of books where this is unavailable.
```

Kindle (2022 release)
$ 99.99 - Seen October 3, 2023
https://www.amazon.com/kindle-the-lightest-and-most-compact-kindle/dp/B09SWW583J

Method 5 - Choose books not available in KFX format
https://www.mobileread.com/forums/showthread.php?t=283371
```
Books that are unavailable in KFX format.
Unfortunately these are only a very small subset of the Kindle books available on Amazon.

```

Method 6 - Use an old version of Kindle for Android
https://www.mobileread.com/forums/showthread.php?t=283371
```
The Kindle for Android app can be run using emulator software on just about any system. 
An Android device is not required.
```

DRM workaround: Kindle for Android 
https://www.mobileread.com/forums/showthread.php?t=352278
```
SEE the DETAILS in this ARTICLE.
```

DRM workaround: Kindle for Android
https://www.mobileread.com/forums/showthread.php?t=352278
1. Acquire SDK Platform Tools to get adb.exe (Android Debug Bridge)
    and an APK for an older version of Kindle for Android, 4.17 and below.. 
    I used 4.16.0.75.

```
Amazon Kindle 4.16.0.75-1145045067
MD5 hash of 1ebe31041db4824c9f83a43d04d74668 
verify MD5 hash at https://emn178.github.io/online-tools/md5_checksum.html
FILE com.amazon.kindle-4.16.0.75-1145045067-minAPI16.apk
http://www.oldversion.com/android/com-amazon-kindle-4-16-0-75-1145045067

Note that there are reports that the apk won't work for Android 11, 
and that at least on Android 10 the app may attempt to force the user to upgrade to download books. 
32-bit Nougat on Bluestacks is confirmed to work.

one user reports success using 4.16.0.75 in Android Emulator 
(part of Android Studio), albeit with severe performance penalties
```

DeDRM Plugin (v6.7.0)
https://github.com/apprenticeharper/DeDRM_tools/releases/download/v6.7.0/DeDRM_tools_6.7.0.zip
https://github.com/apprenticeharper/DeDRM_tools/releases
This plugin removes DRM from ebooks when they are imported into calibre.
DeDRM_tools_6.8.1/DeDRM_Plugin/DeDRM_Help.htm


2. Follow these instructions to extract your Kindle key and import to DeDRM.
https://github.com/noDRM/DeDRM_tools/blob/master/DeDRM_plugin/DeDRM_Kindle%20for%20Android%20Key_Help.htm
"DeDRM_tools_6.8.1.zip\DeDRM_Plugin.zip\DeDRM_EInk Kindle Serial Number_Help.htm"
```
Getting the Kindle for Android backup file

Obtain and install adb (Android Debug Bridge) on your computer. 
Enable developer mode on your Android device. 
Connect your device to your computer with a USB cable.
Open up a command line (Terminal on Mac OS X and cmd.exe on Windows) 
adb backup com.amazon.kindle
(A file "backup.ab" should be created in your home directory.)

```

Android 7.0 was officially released on August 22, 2016
https://en.wikipedia.org/wiki/Android_Nougat

one user reports success using 4.16.0.75 in Android Emulator 
(part of Android Studio), albeit with severe performance penalties.


3. After downloading your book
```
Look in /Android/data/com.amazon.kindle/files/ 
for PRC files inside ASIN-labelled subfolders. Copy it out and DeDRM it.

(Bluestacks has a preinstalled "Media Manager" app that allows you to
 export the file to the OS.)
```

NOTE, 64bit bluestacks method . . .
```
DuckieTigger 

Download Kindle for Android version 8.51.1.0 
(oldversion doesn't have it, 
I used apkpure Kindle for Android version 8.51.1.0, 
the arm64-v8a will only work for 64bit Bluestacks 
and 
the armeabi-v7a will work for 32bit and 64bit Bluestacks)
FILE Amazon Kindle_8.51.1.0(1.3.272119.0)_Apkpure_arm64-v8a.apk
FILE Amazon Kindle_8.51.1.0(1.3.272119.0)_Apkpure_armeabi-v7a.apk
https://apkpure.com/amazon-kindle/com.amazon.kindle/variant/8.51.1.0(1.3.272119.0)-APK

```

Using
```
Using (from that Retro Software Site)
BlueStacks 5.0.220.1003 32-bit Android
a.k.a BlueStacks 5.0.220.1003 N32

Download  BlueStacks App Player
BlueStacks App Player 5.0.220.1003
BlueStacks_App_Player_v5.0.220.1003.exe
https://www.filepuma.com/download/bluestacks_app_player_5.0.220.1003-28999/

OnePlus 5
OS	Android 7.1.1 (Nougat), upgradable to Android 10, OxygenOS 10.0.0
https://www.gsmarena.com/oneplus_5-8647.php

NOTE: Bluestacks 5 (After I turn the "Android Debug bridge" ON)
Settings -> Advanced -> Android Debug bridge -> Connect to Android at 127.0.0.1:5555
```
