# my-crispy-arcolinux-configs
the configs i use with my arcolinuxd install

general instructions (assuming you are using arco linux):

## for the conky:
put the file in the following directory: `/home/*user*/.config/conky/`

then, add the following line to the top of the .conky-list.txt file in the same directory
`BloodMoon.conkyrc`

after that, in your terminal, do `$ conky-rotate -n` until the conky shows up, 

after that you can use `$ conky-toggle` once or twice and it should then stay there, and autolaunch when you log in

## for the cursor theme:
put the BloodMoon-Cursor folder into one of the following directories

-`/home/*user*/.icons/` if you only want one user to be able to use it

-`/usr/share/.icons/` if you want all users (including root) to be able to use it

from here enable to mouse theme just like you would for any other mouse theme, for example, xfce users can open Mouse and Touchpad app from the menu, and select it under the themes tab

trouble shooting will likewise be the same as any other mouse theme, and depends on your DE among other things


if you intend to modify the cursor theme, start by modifying the .png's in the source directory, once you've modified them to your liking, open your terminal, cd into the source directory, and execute the following command `make`, the rest should be handled automatically by the Makefile in the source directory
    
## for the termite theme:
simply put the file in the following directory: `/home/*user*/.config/termite/themes/`and you should then be able to select the theme with the Arcolinux Tweak Tool
  
## for the SDDM theme:
put the BloodMoon folder into the following directory: `/usr/share/SDDM/themes/`

to select the theme, you're going to have to nano (or vim, or whatever) into the SDDM config file at the following file path: 
`/etc/sddm.conf`

once that file is opened, find the [Theme] section of the file, and change the line `Current=` (should be around line 33) to `Current=BloodMoon`

you can preview this login screen by using the following command in your terminal:
`$ sddm-greeter --test-mode --theme /usr/share/sddm/themes/BloodMoon/`
  
## for the GTK theme:
put the BloodMoon folder into one or both of the following directories:

-`/home/*user*/.themes/` if you only want one user to be able to use it,

-`/usr/share/themes/` if you want all users (including root) to be able to use it

to turn on the theme, simply open your DE's version of the Appearance app, the BloodMoon theme should show up in the menu, select it, 		

[if you use XFCE] (other DE's may have similar issues aswell, i don't know)
from there, you're going to want to open the panel customization gui, navigate to the appearence tab, and turn off dark mode (i know, it doesn't really make sense), this whole toggling dark mode for specific apps should work for any app who's gui is a white/red color sceme instead of the intended black/red

you can also modiyfy the settings.ini file in
`/home/*user*/.config/gtk-3.0/`
to set the theme manually, this also applies to the cursor theme

## for the suckless programs (DWM, ST, SLStatus
copy the folders into `home/*user*/.config/` then, cd into the directories and run the following commands: $ `make` and $ `sudo make clean install`
then reboot, 
you can also compare my files with your own using meld, or some other utility

don't copy my autostart.sh file over your own unless you know what you're doing, same goes for the sxhk folder (which manages hotkeys on arco linux)

## for the scripts
each script should have its own readme, read that for usage instructions, documentation, usage, etc.

## misc info
-There are pictures of these configs in action in the Wiki tab

-also, you can find the image i used as my desktop background in the SDDM folder, named 'background.jpg'

-if you have any suggestions, feel free to let me know in the issues tab

