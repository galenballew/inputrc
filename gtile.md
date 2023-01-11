How to
Install extension
Option 1: Through the website
Go to https://extensions.gnome.org/extension/28/gtile, install the chrome extension, refresh, tick the toggle on. 

Option 2: Build from source
Do this stuff:

$ sudo apt install bazel

$ update-alternatives --install /usr/bin/python python /usr/bin/python3 1

$ cd ~/Downloads

$ git clone https://github.com/gTile/gTile.git

$ cd gTile

$ bazel run :install-extension

Log out and log back in. (If you don't want to log out, you can restart gnome shell, which keeps all your windows open. Type Alt+F2, then type r and hit enter.)

Find "Tweaks" application, Launch Extensions and enable gTile


(Instructions from here https://yaqs.corp.google.com/eng/q/4471454305420836864#a1 and https://github.com/gTile/gTile#installation-from-source) 


Customize the settings
Remove the default keybinds (Settings -> Keyboard -> Keyboard shortcuts => "View and Customize Shortcuts") for Restore Window, View split on left, and View split on Right. I set Maximize Window to Super+Space (this one was just to have it, I don't think it's necessary)


In the Extensions Application (either by searching the computer for the native "Extensions" app or going to https://extensions.gnome.org/local/) go to gTile and go into settings (either "Settings" button or the wrench icon. Then in the "Basic" tab I set Grid sizes to only 2x2. After this you need to hit Super+Enter to bring up the gTile window then hit Space to switch to that grid. A little awkward, but we get there. Also enable Global resize presets.


In the gTile Accelerators tab keep the top 4 (particularly Cancel tiling because rebinding Escape is a pain), but I cleared everything else with backspace. Then we set the important 4 commands:

Preset resize 1: Super+Right

Preset resize 2: Super+Left

Global move window down: Super+Down

Global move window up: Super+Up


In the gTile “Resize Presets” tab set:

Preset Resize 1 : 2x1 2:1 2:1, 2x2 2:1 2:1, 2x2 2:2 2:2

Preset Resize 2 : 2x1 1:1 1:1, 2x2 1:1 1:1, 2x2 1:2 1:2


(See the notes section below for what this means)


Now if you have a window you can do these sequences:

1) Put it on the right half of the screen

Super+Right

2) Put it on the top right quadrant

Super+Right -> Super+Up

or (for redundancy, probably not necessary)

Super+Right -> Super+Right

3) Put it on the bottom right quadrant

Super+Right -> Super+Down

or (for redundancy, probably not necessary)

Super+Right -> Super+Right -> Super+Right 

4) Maximize

Super+Space


Notes
wtf do Preset Resize settings mean
They’re set up in comma delimited sections, each of which look like:

2x2 2:1 2:1

AxB C:D E:F


AxB - The grid is A by B, so A columns and B rows. The example is 2x2, so the screen is split into quadrants (a 2x2 grid).

C:D - The top-left grid space to move the window to on this keypress. The example is 2:1, so the window will move to the 2nd column, 1st row.

E:F - The bottom-right grid space to move the window to on this keypress. The example is 2:1, which is the same as the top-left, so it’ll just fill the 2nd column 1st row space. If this were bigger you could do a bigger grid or rectangles or whatever.


When you hit that keybind it cycles between the sections
