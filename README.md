## NOTE: This is my fork of `wal`  by Dylan Araps. Go Credit him for the idea.

From his README.MD:
`wal` is a script that takes an image (or a directory of images), generates a colorscheme (using `imagemagick`) and then changes all of your open terminal's colorschemes to the new colors on the fly. `wal` then caches each generated colorscheme so that cycling through wallpapers while changing colorschemes is instantaneous. `wal` finally merges the new colorscheme into the Xresources db so that any new terminal emulators you open use the new colorscheme.

Repo link: https://github.com/dylanaraps/wal
​
`wal` can also change the colors in some other programs, check out the [Customization](#customization) section below.
​
**NOTE:** `wal` is not perfect and won't work with some images.

# wal

The fork is updated to write the generated color scheme to the i3, sway, termite and Xresources config files and the following scripts in order to store them permanently.
The color configuration sections in the scripts and config files are currently empty. When you run the script in the format `wal -i /Path/To/Your/Wallpaper.png` the colors are written to the particular sections of the configuration files of the above mentioned applications.


### Dependencies

- `bash`
- `imagemagick`
    - Colorscheme generation
- `xfce`, `gnome`, `cinnamon`, `mate`
    - Desktop wallpaper setting.
- `feh`, `nitrogen`, `bgs`, `hsetroot`, `habak`
    - Universal wallpaper setting.
- `xprop`
    - Used to detect which DE wallpaper setter to use.
    - Only required if you're running a DE.


## Usage

Run `wal` and point it to either a directory (`wal -i "path/to/dir"`) or an image (`wal -i "/path/to/img.jpg"`) and that's all. `wal` will change your wallpaper for you and also set your terminal colors.

```sh
Usage: wal [OPTION] -i '/path/to/dir'
Example: wal -i '${HOME}/Pictures/Wallpapers/'
         wal -i '${HOME}/Pictures/1.jpg'

Flags:
  -a                      Set terminal background transparency. *Only works in URxvt*
  -c                      Delete all cached colorschemes.
  -f '/path/to/colors'    Load colors directly from a colorscheme file.
  -h                      Display this help page.
  -i '/path/to/dir'       Which image to use.
     '/path/to/img.jpg'
  -n                      Skip setting the wallpaper.
  -o 'script_name'        External script to run after 'wal'.
  -q                      Quiet mode, don't print anything.
  -r                      Reload current colorscheme.
  -t                      Fix artifacts in VTE Terminals. (Termite, xfce4-terminal)
  -x                      Use extended 16-color palette.

```


