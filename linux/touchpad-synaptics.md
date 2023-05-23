# Installation

The synaptics driver can be installed with the package `xf86-input-synaptics`

```sh
sudo pacman -S xf86-input-synaptics
```

# Configuration

Default configuration file is located at `/usr/share/X11/xorg.conf.d/70-synaptics.conf`. Users can copy this file to `/etc/X11/xorg.conf.d` and edit it to configure the various driver options available.

Frequently used options

The following example file configures some common options, including vertical, horizontal and circular scrolling as well as tap-to-click:

```sh
Section "InputClass"
Identifier "touchpad"
Driver "synaptics"
MatchIsTouchpad "on"
Option "TapButton1" "1"
Option "TapButton2" "3"
Option "TapButton3" "2"
Option "VertEdgeScroll" "on"
Option "VertTwoFingerScroll" "on"
Option "HorizEdgeScroll" "on"
Option "HorizTwoFingerScroll" "on"
Option "CircularScrolling" "on"
Option "CircScrollTrigger" "2"
Option "EmulateTwoFingerMinZ" "40"
Option "EmulateTwoFingerMinW" "8"
Option "CoastingSpeed" "0"
Option "FingerLow" "30"
Option "FingerHigh" "50"
Option "MaxTapTime" "125"
Option "VertScrollDelta" "-111"
EndSection
```

For more options visit <https://wiki.archlinux.org/title/Touchpad_Synaptics>
