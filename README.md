# spin

a small utility to assist in setting usage modes of laptop-tablet devices

## about this fork

This is a fork of wdbm/spin. I'm currently working in the yoga12-2nd-gen branch, to get everything working properly with my Thinkpad Yoga 12 2nd Gen machine under Ubuntu 15.10. So far I've done the following changes:

- Improved the handling of the accelerometer using vector math, so it detects the correct orientation.
- Moved all changes to the screen rotation to the mani process, and use messaging from the subprocesses to tell the main process what to do.
- Added support for the rotation lock key on the side of the ThinkPad Yoga 12.
- It now waits for the touchscreen to be ready, before attempting to rotate it.

Known issues:

- The display position detector triggers once in tablet mode, when the accelerometer detector is not running, but twice (in tent and tablet mode) when it's not. This confuses the script, so you sometimes wind up in laptopt mode, when you should be in tablet mode, and vice versa.
- Sometimes the keyboard gets turned off, when it's in laptop mode. I think this is related to the above issue.

Other than that, it's almost done.

## prerequisites

```Bash
sudo apt-get -y install python-docopt
sudo apt-get -y install python-qt4
```

## quick start

This utility can be run in its default graphical mode or in a non-graphical mode. The graphical mode is engaged by running

```Bash
spin.py
```

while the non-graphical mode is engaged by using the option ```--nogui```:

```Bash
spin.py --nogui
```

By default, this utility disables the touchscreen on detecting the stylus in proximity and it changes between the laptop and tablet modes on detecting toggling between the laptop and tablet usage configurations. These default behaviours are provided by both the graphical and non-graphical modes of this utility. This utility should be initiated in the laptop usage configuration.

## compatibility

This utility has been tested on the following operating systems:

- Ubuntu 14.10
- Ubuntu 15.04

This utility has been tested on the following computer models:

- ThinkPad S1 Yoga
- ThinkPad S120 Yoga

There is evidence that it does not run with full functionality on the ThinkPad Yoga 14.

## acceleration control

There is an experimental acceleration control included which is deactivated by default. It can be activated by selecting the appropriate button in the graphical mode. Use it with caution because it can result in distortion of the display, including display blackout.

## future

Under consideration is state recording in order to avoid execution of unnecessary commands, better handling of subprocesses, clearer logging and a more ergonomic graphical mode.
