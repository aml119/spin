# spin

a small utility to assist in setting usage modes of laptop-tablet devices

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
