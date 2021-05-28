I've decided to make this handbook to hopefully solve the issues that many people have been running into constantly. It's in my status on Discord. Feel free to bookmark this just in case it's not. If there's another issue I can add, feel free to DM me (MJ, the Spirit#4655).


Each issue will have a problem, a description as to why this happens, and the solution to fix them. If you want to quickly jump to a problem, feel free to press Ctrl + F and type up your issue.


Last updated: 24th May 2021


________________




Problem 1: The video player/maker shows only a white screen! (All LVMs)


Description: This is a problem with website permissions with your web browser, where it mistakes the site as "potentially unsafe".


Solution: Go back to the video list, then right-click anywhere. There should be a right-click menu where "Inspect" is present. You'll want to click that, which opens up the DevTools. Go to Network in the tools, then attempt to edit any video. If you're using old Flash, click "Run anyway". Now go back to the DevTools and go_full.swf should be red. Double-click that even if it's not. Click the link that says "proceed to localhost (unsafe)". The go_full.swf file may start downloading, but feel free to cancel it. When you go back to the video list and attempt to edit a video, it should work normally now.

Non Wrapper: Offline LVMs/ Localhost LVMs (such as GA4SR, GoAniFire, GoAnimate Wrapper etc):
Check your network tab and see if there’s a 404 error in a Github server. If there is a 404 error, then try finding a good GitHub server and edit config.json: 
Example:




 {
        "SWF_URL": "https:/(USER).github.io/(REPOSITORY NAME)/animation/414827163ad4eb60",
        "STORE_URL": "https:/(USER).github.io/(REPOSITORY NAME)/store/3a981f5cb2739137",
        "CLIENT_URL": "https:/(USER).github.io/(REPOSITORY NAME)/static/ad44370a650793d9"
}
Save it, restart your npm. 




* Credit to BluePeacocks for this ^




________________




Problem 2: My imported assets are loading forever/doesn't play! (Wrapper: Offline)


Description: The importer doesn't have a 100% success rate. Sometimes when it tries to import the thing, it updates the theme.xml file in the import folder but doesn't actually copy the file over.


Solution: Select the file that you just imported, then copy it by pressing Ctrl + C or right-clicking it and clicking "Copy". Go to wrapper-offline\server\store\3a981f5cb2739137\import in your Wrapper: Offline folder. If you want to add a sound effect to your folder, you paste the copied asset to the sound folder. For props, they go in the prop folder. Go back to the LVM and the asset should play or load correctly. If not, feel free to save the video and restart the video maker.


Tip: Errors like these could be the cause of spaces in the file names. It's recommended that you use only lowercase letters, numbers or underscores.


________________




Problem 3: In Your Library, imported backgrounds don’t show! (Wrapper: Offline 1.3.0+/GoAnimate Wrapper)
Description: You’re trying to import a background the original importing way (true importing)
But after importing a background and typing “bg” after uploading, you don’t see any backgrounds on the ”Your Library” tab.


Solution: The Your Library importer coded by VisualPlugin doesn’t import backgrounds straightaway. To make this work, after uploading a background (BY THE IMPORT BUTTON IN THE LVM NOT THROUGH BY IMPORT.BAT), you need to save your video with the imported background and then play it and then edit it. (video tutorial shown below)


https://youtu.be/DaY2wr5kFIA


________________




Problem 4: Flash gives me an image that redirects to the EOL page! (All LVMs)


Description: You're trying to use the LVM on a version of Flash that has the timebomb (32.0.0.371 and later). There is a whitelist mode for it but I haven't looked into that yet.


Solution: Uninstall the current version of Flash that you have using the uninstaller, provided here. You can use Windows to uninstall it, but remnants of it will remain if you do so. Don't forget to close all your browsers (Chrome, Firefox, Opera, etc.) before uninstalling. It'll say to restart your computer, but this is optional. Next, download the old version of Flash using this download link here. Run the installer and follow its instructions. When installation is complete, don't forget to select "never check for updates" as shown here:
  
This is to prevent Flash from updating itself back to the time-bombed version(s), hence why a lot of people have been saying that Flash 18 is time-bombed. It's definitely not.


People have also been saying that the KB4577586 Windows update will permanently remove Flash, but I tested the update myself. The only thing that happened was the Flash option being removed from the Control Panel. Standalone versions of Flash work perfectly as if the update was never installed to begin with. All it does is just remove the version of Flash that comes with Windows 8 and 10. KrisAnimate and I confirmed this.


An old Flash version for Mac is located here.


________________




Problem 5: The video is laggy for me… (All LVMs)


Description: The problem with screen-recording them is the fact that Flash can take up a lot of resources due to it being outdated (but nostalgic). You're mainly used to exporting the videos, which removes most of the lag but has a rare chance of freezing mid-way due to complexity.


Solution 1: Close any applications (especially resource-hogging ones) that may be running in the background. It may be advisable to keep your antivirus running due to Flash's security risks and holes, but disable it at your own risk. Don't forget to either close all instances of Discord as well, which reduces security risks and removes the problem of pings playing in the background.


Solution 2: Resize the video player to a smaller scale. I normally resize it so that the video is 960x540 (excluding the title bar), which gives 480p quality with a good framerate with 4 characters or less.


Solution 3: Open a video from the video list, then right-click its window while the page is white. When done correctly, an option that says "quality" will appear. Set that to medium. Doing so removes some of the processor intensive graphics to make your video run smoother. Don't set it to low otherwise the video can look gritty and bad.


Tip 1: Try to reduce the number of characters that you use for your videos. A soft limit would be around 4 characters in one scene. Not recommended to go higher than 7, especially if they're all moving at the same time.


Tip 2: You can also reduce the quality in the video maker as well, reducing lag.


________________




Problem 6: The video is corrupted for me and won't play! (All LVMs)


Description: This can be the cause of many different problems; specifically, parsing issues. I've listed them down below:
1. The video contains special characters, such as smart quotes (’), emojis (😊) or degree symbols (°), especially in TTS voice clips. Don't forget that this can happen with text boxes as well.
2. You accidentally made a new line in the TTS box when you attempted to generate the voice clip.
3. You're trying to load a video that contains assets/custom actions that another LVM had, which don't exist in your LVM.


Solution 1: Download the XML video that you want to fix. Then, open it up using a text editor. Notepad++ is strongly recommended, and we'll use that. You can use OG Notepad as well for this, but it can freeze if you attempt to edit the XML file using that.


Press Ctrl + F, go to Replace and put the smart quote above (copy/paste it) in the "find what" box. Then, put a regular quote in the "replace with" box and click "replace all". Next, go to Find and search for "tts". Click "find all in current document". Now, scroll down through your list of voice clip text that you provided and check for any misplaced new lines. Here's an example.
  

The above screenshot needs to be corrected to the below one, by backspacing before the "]]" several times:
  



Solution 2: If the above solution didn't work, then you would need to try different LVM websites that have different asset libraries. XML videos aren't always compatible with some asset libraries, hence why it may get stuck as it's buffering. GoAnifire and GoAnimate Wrapper both have large asset libraries that can load up many videos, but sometimes they might not work. If you have any working online LVM websites, try them. They may load the video.


Solution 3: Download the action pack selector file from here, then move it to the utilities folder in your copy of Wrapper: Offline. Run it (click "Run anyway" if SmartScreen prevents the file from running), then follow its instructions provided. It gives you action packs from OG CW, Kenny's Wrapper, GoAnifire (glitchy) and GA Wrapper. It also saves you the trouble of having to navigate through multiple folders just to replace a file and you only have to download this .bat file once (unless you lose it somehow).


Solution 4: If none of the solutions worked, then you'll have to recreate the video from scratch. However, you can save a little bit of time with recreation by using this video to help you. You can save the scene data along with the characters and motion paths, leaving you with just the voices to regenerate and re-sync to characters in every scene.


Tip: Make sure you create backups of your videos often. It autosaves every 10 minutes as long as a change has been made in that time.


________________




Problem 7: The voices, effects and fullscreen button aren't working! (All LVMs)


Description (voices): Yeah, the voices can go down every now and then. I don't have much experience with TTS voice file code, but one day that'll change.


Description (effects): This is a known issue with the parse.js file that has been fixed in GA Wrapper (second instance).


Description (fullscreen button): Just like the effects, this was a known issue with page.js, but this could be worked around by pressing F11 on the keyboard while the video was loading to achieve the same effect.




Solution (voices): There's no clear solution for this; a suggestion would be to either try again later (such as in a few minutes or hours) or try talking to someone who is good at TTS voice modding, such as JoshToons, a GA4SR developer.


Solution (effects): Download the modded parse.js file here and replace the current file with the modded one in wrapper\data. Restart the Wrapper clone, launch the video, and the effects should work.


Solution (fullscreen button): Download the modded page.js file here and replace the current file with the modded one in wrapper\data. Restart the Wrapper clone, launch the video, and attempt to press the fullscreen button. It should work as intended.


________________




Problem 8: The import script is forcing me to import files that I didn't want to import! (Wrapper: Offline)


Description: If you attempt to import a file, it makes a copy of what you're trying to import and puts it into the import_these folder. If you choose not to import the files shown, it exits the script.


Solution: Go to wrapper-offline\utilities\import_these and delete or move everything except the imported (and conflicts) folders to another location, then try to open the script again. It should work like normal.


________________




Problem 9: Localhost refused to connect?! (All LVMs)


Description: This issue happens because of a number of reasons, ranging to the npm crashing to Node.js taking long to load.


Solution 1: If you just started your computer, followed by your Wrapper clone and Node.js, then you might need to wait a bit before refreshing the page. Wait a minute and try again.


Solution 2: The npm might have crashed due to the packages being corrupt or not installing correctly. For Wrapper: Offline users, turn on verbose mode first. Look for settings.bat, run it, then enter 1 in the script to turn it on. Close that down then restart (or start up) Wrapper: Offline. Two extra CMD windows will be open; npm and http-server.
 
If the npm window gives out errors, put the commands "npm uninstall" and "npm install" in that order. If it's the http-server window, add "http-server -g" to the end of both commands before entering them.


Solution 3 (Wrapper: Offline 1.3.0+): After saving your video, if refreshing doesn't work, remove everything except "localhost" and the port number from the URL and the video list should appear again.


Solution 4: (Localhost LVMs ga4sr, gaw etc): Check the NPM console that causes an npm crash. The console should show an error in your command prompt,
Example: 
  

________________




Problem 10: Why does the server take too long to load when starting Wrapper Online/Offline server?


Description: The server's cache from audio tracks, videos and thumbnails can end up hogging all the memory. 


Solution: Delete the contents of the _CACHÉ folder. Go to it, then press Ctrl + A to highlight everything, then press the Delete key on your keyboard. It doesn't really matter if the _NO_REMÖVE file is deleted because that is to prevent the GitHub repository from deleting this directory. This also frees up some space on your hard drive as well.


________________




Problem 11: How come the characters aren't loading when I access different categories of a theme? (Wrapper: Offline)


Description: The LVM isn't able to load the character data from the server\characters directory. This includes Mega CW 2.0, which is included in Wrapper: Offline 1.2+.


Solution 1: Go to wrapper-offline\server\characters and look for a file that says "required.zip". Right-click it and extract its contents, then save your video and refresh the LVM. When you check in the category where the characters are supposed to load, they should load properly.


Solution 2: If that didn't work, then it could be due to your file width being any number other than 1000. Head over to wrapper-offline\wrapper and open env.json. Where it says "FILE_WIDTH", change its value to 1000, then press Ctrl + S to save it and restart Wrapper: Offline. The characters should load properly.


________________


________________


________________




This is also the FAQ for questions to be answered here. Each question will also contain the answer to them as well.


________________




Question 1: Can you use an old version of web browsers to use Flash/the LVM?


Answer: Yes! The last version of Chrome that works with Flash is 87.0.4280.66, which is a version after Flash's EOL, dating 2020-11-17. From what I can gather, it taps into the standalone version of Flash that has been installed on the computer, such as Flash 18. I haven't tested other web browsers yet, because I mainly use Chrome. If you're not able to run this specific Chrome version many years in the future, Pale Moon or ungoogled Chromium is always a solution.


________________




Question 2: How do I remove/replace the watermark on my LVM clone?


Answer 1 (for yourself and online LVMs): You'll need Requestly for this. Open the application and create a new Replace rule. Next, put "/goapi/getMovieInfo/" in the Replace box and "/goanimate/GetMovieinfo.xml'' in the With box. Name the rule anything you'd like (probably something related to removing the watermark), then turn it on and save it. As long as this rule is active, the watermark will be completely removed on all LVMs.


Answer 2 (globally): Go to wrapper\static and open info.json. Press Ctrl + F on Notepad(++) and search for "<watermark style=\". You can then change the information between what you searched for and "/></watermarks>"" to what you'd like to change or remove the watermark entirely, using these codes:


No watermark = visualplugin
2015 logo = twoLines
GoAnimate for Schools = g4s
Free trial = freeTrial


When you're done, save it (Ctrl + S) and restart your Wrapper clone (reloading the video player doesn't work), and the watermark will either be replaced or removed when you play a video next time, depending on your preference.


________________




Question 3: How do I enable debug mode in the LVM?


Answer: Go to the static folder and open page.js. When it's open, search for "ut", which is found 4 times in the file. It's recommended that all their values need to match each other for this to work. You can change the values to what is shown below to trigger their effects:


60 = Enables debug mode
30 = Disables debug mode  
10 = Enables free plan mode (not recommended)


When you've made those changes, save the document (Ctrl + S) and restart your Wrapper clone.


Free plan mode has the following restrictions:
* Only able to make videos that are 2 minutes (or less) in length
* Some settings are missing
* Your Library removes the Starters and Videos submenus  
* Comedy World locks all categories in the character selection menu except custom characters, making them unusable
* The LVM thinks that the account we use is expired, so it’s super limited, and it’s better to upgrade to better uts (doesn’t have userId)


Caution: When you use debug mode in the LVM, it's very important that you avoid using certain features with it, because they will cause the video maker to softlock, forcing you to restart it, because no inputs will work upon choosing them.




Softlock spots:
   * Going to the settings and clicking "Save as Text Component"
   * Going to the theme dropdown list and clicking "Team Library" or "Shared with you".
   * Clicking the "i" in the character list, background list, prop list or even starter list which appears to bring up a menu on editing a character but the buttons can't be clicked on. With the menu softlock, you can press Tab repeatedly to move the highlighter into a text box and type in it, but you can't close the menu at all.




________________




Question 4: How do I copy characters?


Answer: In the URL, put &original_asset_id=(id) at the end (or between "cc?themeId=family" and "&bs=adam" if the second variable exists). Replace (id) with a character ID that's found in the video maker, by hovering over the character that you want to copy while debug mode is enabled.


You can also do this with original character IDs (the ones from the original LVM before it retired and is no longer usable), provided that you have the entire character dump, which can be downloaded here (all files go in server\characters).


Caution: The entire character dump takes up 13+ GB of space on your computer when uncompressed.


________________




Question 5: How do I delete videos that I already made?


Answer: To make it easier, look for the video that you want to delete, then click the play button. You should see its ID in the URL. Next, go to your LVM files (for Wrapper: Offline, check the wrapper folder) and find the _SAVED folder, which contains a list of XML files for characters, movies and thumbnails. Scroll down until you get the movie-(number).xml files, then delete the file that matches the ID that you saw previously. So, for example, if you want to delete a video with an ID of 32, you delete the file movie-0000032.xml from the folder. When you reload the video list, the video should be gone.


________________




Question 6: How do I remove imported assets?


Answer (for those who used Wrapper: Offline's import feature):
Go to wrapper-offline\server\store\3a981f5cb2739137\import, then make a note of the file names that you want to delete. When you're done, delete them. Next, go back to the import folder and open up theme.xml in a text editor. Using the file names that you noted down, press Ctrl + F and type up the file name of the item you deleted, then press Enter. You should be able to find the item that you're searching for.


Next, delete the entire XML line, from "<prop id=" to "sharing="0" />", along with those variables. Repeat for all the files that you've deleted in the folder(s) before. When you're done, save it (Ctrl + S) and close your text editor. Next, open up import.zip, which opens up a WinRAR window containing a duplicate theme.xml file. Drag the recently saved theme.xml file in the import folder to the WinRAR window and press OK when prompted. This will overwrite the duplicate file with the recently saved one. When you refresh the LVM and check your imported assets again, they will be completely removed.


You can also do all this with the manual (harder) importing method, but in wrapper-offline\server\store\3a981f5cb2739137\common instead.


________________




Question 7: How do I change the port on my LVM?


Answer: In your LVM folder, open up env.json and find the variable "SERVER_PORT". By default, with half-offline LVM clones, this port is 80. For Wrapper: Offline, this is 4343. Flashpoint uses ports 12001, 22502 and 22600 for the games and itself, along with its built-in portable browsers that support Flash. So, it's recommended that you change the number to any value other than what's listed above. Save the file (Ctrl + S). Remember to put the colon and the port number after you type "localhost" in the URL every time you want to start it.


If you're using Wrapper: Offline, don't forget to change the original port with the changed one that you want to use. Right-click the start_wrapper.bat file and click "edit" or "edit with Notepad++". When your preferred text editor is open, press Ctrl + F to bring up a search menu and type in "localhost". Whenever you see a result that has a port number that's not 4664 (because this is for the asset server), change that to the number that you set it to in env.json, and keep searching for those results, changing them to your preferred port. When you're done, save the file (Ctrl + S) and restart Wrapper: Offline.


________________




Question 8: How to add custom assets without using the importer?


If you want to import your custom assets in your video maker, you also need to edit common.xml and the zip file, just be careful if only you can choose the swf file for a smoother experience!


To add your assets, be aware you have Adobe Animate or Macromedia Flash Player 8 (recommended), only all is needed to draw an image with a brush tool, after you draw this image, then you export this file as a .swf file and go back to editing with common.xml.
Before you back editing with common.xml, find a prop id, copy it and paste this copied text. After you saved it, make sure that multiple files needed to be saved.


Now it’s time to archive with 7-zip.


Also with 7-zip you can easily archive your files and folders but be aware it’s more than legend! Let’s take to archive common.xml with 7zip and so we can upload from it.
Make sure the compression level is normal, otherwise it will not load any assets, and then you straight upload into GitHub called common folder on store folder. Wait a few minutes… BOOM and now you can see the prop that we drew on it!


________________




Question 9: How to add custom visual effects (special FX) on this maker?


To make custom visual effects on this maker you also need that you’re using Notepad++ and GitHub files on your store folder, which is to upload it. Now you also need to add it to a .swf file on your exported file from Flash, but be aware that the effects that you added are not a transparent or fake effects that doesn’t match either! Only way that it needs you from Flash to create this effect, you also use transparent, overlay, opacity, composited modes, etc.


Let’s make a custom visual effect! Now you just draw a red square or other gradient color square, before you draw on it, make sure that you are converted into a symbol, when you convert into a symbol, you will also gain composited modes on this symbol (and actionscript too)! Now you try to select a composite mode like darken, difference, lighten, overlay, invert or you know anything about composite modes like that, you can just add more composite modes on another symbols that you add them, the most way is much better to smooth your video for adding a dual composite modes on another symbols which you converted them! It’s now to upload an effect from common.xml by pasting an effect from text.


Make sure that value is not the same as the effect, just try to number it and just save it.


Upload on GitHub, also you forgot to upload on effect.zip, use 7-zip again and drag the file from a compressed file.


Upload effect folder on GitHub and upload effect.zip on GitHub, make sure you updated the common.xml and theme.zip.


Now wait for a few minutes… Just find a new effect, you can actually see the blue unknown effect, adding a scene also removes the effect once again you will re-add this and it will happen to remove the effect automatically again, because this effect is not recognized and only one scene, now just save the movie and play it. It’s completely worked as well and people can definitely use it as well (Custom Visual Effects explained from WOG (“Wrapper Online Gold”)).


________________




Question 10: How do I install Wrapper: Offline 1.3.0+?


Answer 1: Simply download the installer here, then click on Code, then Download ZIP. When that's downloaded, extract the folder inside of the ZIP to a good location, such as the desktop. Go into that folder in the file explorer and install Git. When installation of Git is complete or if you installed it beforehand, run install_wrapper.bat and follow the instructions. Setup takes around 10 - 30 minutes depending on your Internet speed. When it's downloaded, a window should appear showing off some of the Wrapper: Offline files. All you have to do from there is run start_wrapper.bat and accept the disclaimer. You're done.




Answer 2: Download this emergency copy from here. Then, extract the wrapper-offline folder to a good location, such as the desktop. Run start_wrapper.bat and accept the disclaimer. (this is for people that are having trouble installing Wrapper: Offline 1.3.0+ with the installer)


________________




Question 11: How do I export/record my videos?


Answer 1 (globally): You'd have to screen record them since no true exporting feature exists at the moment. I would recommend using OBS or Windows 10's Screen Recorder Pro, both of which have no watermarks or time limit when recording. There is a downside to this, however; the loading screen will likely appear at the beginning of the recording. This can reduce the quality (not resolution) of your video, especially if you don't have video editing knowledge. Most people in the community don't.


Answer 2 (Wrapper: Offline 1.3.0+): In the Wrapper: Offline CMD window, simply press 5 to open up the exporter (alternatively, in the utilities folder, run export.bat). It'll launch and check to see if Wrapper: Offline is still running. If it's not, then it'll give you a prompt to say that it's not running and will run start_wrapper.bat to fix this. Otherwise, it brings you to a menu where you can choose from to look for your movie ID. From there, you can follow the instructions provided, but some things may require an explanation to clear up via screenshots.




  

The script wants you to put in "m-(number)" because it would attempt to read the movie files located in the _SAVED folder just like how videos are played normally in the video menu. Both the video player and recording window use "m-(number)" to load videos and their IDs. Without this argument, the video won't load at all. Same with including ".xml" or the zeros in the input, or if you don't shorten "movie" to "m".


  

If your render previously failed due to you accidentally closing the script, due to a computer crash/update or any other action that disrupts the exporting process, then you can simply continue from where you left off if you choose to continue from what you were working on. For example, you could be recording a video, then FFMPEG freezes/severely lags the computer to no end, forcing a restart. You could continue from the Avidemux step rather than having to re-record the entire video from scratch, saving some time with recovery.


  

Some people prefer to not have their videos recorded in widescreen, mainly because it tends to cut off the top and bottom frames of the window. It'll implement the "isWide=" argument into the URL to force the video to load in 14:9.


  

People may prefer using different browsers for recording their videos, but they can also use their default one if need be. Could be because of browser engine layouts or because they can affect the video's frame rate.


  

Doing this ensures that the video would be saved as an AVI file, which is a lossless file type. The sacrifice of it is its large file size. Just copy the settings that you see below.


  





  

The Filters menu will only open with the hotkey combination shown when you matched the video settings that's shown above. Otherwise, nothing happens. The menu itself should look something like this:


  



  

Let's look at the crop menu, since that's where you need to go next. The screen recorder records the entire desktop rather than just a window at ~25fps, so using the tool shown above (along with the counters highlighted with a circle), you can crop the video so that only the Wrapper video itself is present in the exported video. The part of the video in green is what will be cut out when the video is saved later on. When you're done, simply press OK to save the filter. You can also use the preview button to test out the crop.


  

The A and B buttons shown can be used to cut parts out of the video. It highlights the part of the video that would be saved, while anything outside of the box is simply removed. Basically, you're marking the start and end positions of your edited video to remove the loading screen(s) at the beginning and the ending pause when GoAnimate/Wrapper videos reach its end. 


  

Now you just need to save it in a location - preferably utilities\misc\temp. You can save it anywhere but saving it here makes it easier for the exporter. Either click the save button or Ctrl + S after tinkering with the A + B buttons, and wait for the video to be processed.






  

This is dependent on whether or not you recorded your video in widescreen/standard before. Basically, what this does is upscale your video to match the resolution shown depending on what you chose for this.


  

Wrapper: Offline 1.3.0+ has a custom made outro that appears when the video ends just like how GoAnimate does it (Vyond doesn't, surprisingly). You don't have to have it if you don't want to, of course. Once you've entered a name for your video, the final step of exporting will begin. If you choose to not have an outro, the process would be much quicker since it just encodes the video and that's that. But if you choose to have one instead, then it takes a little bit longer (depending on how long your video is). It goes through 4 different processes with FFMPEG:


   1. Encoding the input into a proper format (exports video)
   2. Encoding the video to .ts, to make concat work properly
   3. Merging the outro video file and the exported video with the concat command
   4. Converting the video from a .ts file to an mp4 file (specifically; an H.264/AAC mp4) to make it compatible with most common video editors


After all this, your video should now be exported and in 1080p. If you're curious to know what the outro looks like, it looks like this:
  

(there's supposed to be a whoosh sound effect when the logo comes in)