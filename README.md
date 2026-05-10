# change-gdm-background

This script automates the process of setting an image or color in GNOME Display Manager 3 background
which comes by default with Debian, Ubuntu or Pop OS.

## Warning

This script wont work with any older version of Debian, Ubuntu or Pop OS because they have a different
way of dealing with gdm settings.

It also won't work if your system is set to a custom gdm3 theme. You will have to reset to the
default configuration of gdm3 before using the script.

This tool was made specifically to work with Debian, Ubuntu or Pop OS 20.04, 20.10 and 21.04 as it now
bundles all configuration files inside a .gresource file.

If you are going to set an image file that has spaces in its file name or folders, remember to
escape them with backslashes.

## Installation

First, you will need to install libglib2.0-dev-bin with `sudo apt install libglib2.0-dev-bin`
Then, you can download the script with the command below:

```sh
wget github.com/z7z8th/change-gdm-background/raw/master/change-gdm-background
```

And set it as an executable with `chmod +x change-gdm-background`

## Usage

```sh
$ sudo ~/src/garbage/debian-sys/usr/bin/change-gdm-background

Image file not found or wrong color hex code.
Please, submit a .jpg/.png/.svg image file or a valid hex code.

Usage:
  sudo ./change-gdm-background [-i /path/to/image.*g] [-d /path/to/wallpaper/dir] [-c color_hex_code] [-r] [-b] [-R]
    -i path              Path of background image
    -c hex_color_code    Hex color code
    -r                   Restore original theme
    -b                   Set to latest bing wallpaper automatically, /home/xxx/Pictures/BingWallpaper/*
                         Should be used with gnome-shell bing wallpaper extension:
                         https://github.com/neffo/bing-wallpaper-gnome-extension
    -d dir               Set to newest wallpaper in folder
    -R                   Randomly select wallpaper

Typical usage:
# randomly select a bing wallpaper
sudo ./change-gdm-background -bR

# randomly select a wallpaper in folder
sudo ./change-gdm-background -d /home/xxx/Pictures -R

# set to pure color
sudo ./change-gdm-background -c 6f876d

# restore original theme
sudo ./change-gdm-background -r

```

### Multi-screen support

if you use two or more monitors you may see a streched image through the displays as if they were
    one screen. This is the default behavior of GDM3 when dealing with multiple displays.

I found a way to configure GDM to work in other modes like mirror or even single display
[here](https://github.com/thiggy01/change-gdm-background/issues/15), avoiding the joining of them.

## Donation

If you feel this tool was useful and want to show some appreciation, you can donate via
https://ko-fi.com/thiggy01.

