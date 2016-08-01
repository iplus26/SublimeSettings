# Overview

I installed many packages in Sublime Text, and sometimes modify the preferences settings on different computers or accounts. As we all know, Sublime Text folder is in `~/Library/Application Support/Sublime Text 3/` which means that settings using by even different accounts on one computer can not be shared, not to mention what a miserable life you're living if you are using Sublime Text on different computers. Officially, there are two ways are suggested to sync the settings among accounts ---- using git and Dropbox. For some reasons, Dropbox is not an ideal way in China, so I try the former way. 

I'm a web front-end developer so that my settings may be only suitable for guys like me, writing HTML, JavaScript, CSS and frameworks like jQuery, AngularJS and so on. You can be free to fork this project and set up as you wish. 

To see which packages I've installed in my Sublime Text, check out [Package Control.sublime-settings](https://github.com/iplus26/SublimeSettings/blob/master/User/Package%20Control.sublime-settings).

# Get You Hands Dirty

After you set up your repo on your 1st account, let's see how to **sync your settings to the 2nd account**.  

1. <kbd>Command + Q</kbd> to quit your Sublime Text first. 
2. `cd ~/Library/Application\ Support/Sublime\ Text\ 3 && rm -rf *`. Delete the current settings and free yourself. 
3. `git clone https://github.com/iplus26/SublimeSettings.git Packages && cd Packages`.
4. Comment out the following lines in `Packages/User/Preferences.sublime-settings`: '`//"color_scheme": "Packages/Material Theme/schemes/Material-Theme.tmTheme", ... // "theme": "Material-Theme.sublime-theme",`'. (Sublime Text won't find the theme and color scheme before we install the Package Control and Material Theme package)
5. Open Sublime Text 3 and install Package Control (You may have installed before but you just delete it :P). Follow the steps on [PackageControl.io](https://packagecontrol.io/installation). 
6. Wait for a minute that Package Control will automatically install the packages listed in `Packages/User/Package Control.sublime-settings`. You can check out the progress in console or <kbd>command + shift + P</kbd> and type `list` to list installed packages. 
7. Restart Sublime Text to make sure everything works fine. 
8. `git checkout User/Preferences.sublime-settings` to use the theme and color scheme we commented out before. 
9. Keep in mind that update the git repo whenever you've changed the settings before you switched to another account. 
