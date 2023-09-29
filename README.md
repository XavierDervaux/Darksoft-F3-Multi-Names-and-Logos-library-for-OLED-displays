# Darksoft F3 Multi Names and Logos library for OLED displays
Darksoft released the second version of the F3 Multi with the option to add an OLED display in parallel or instead of the traditional LCD display for game selection. This brings the possibility to have game logos show on the display when selecting a rom.
Since I had issues finding a ready to use F3 Multi logo library, I decided to make my own and share it in hope that it might help someone else.

## Installation
Simply copy the `games` folder at the root of your SD card, this will install the NAME and logo.bin file for every game in the repository.
Please note that no roms are provided in this repository, you will need to source your own.

## How to generate the files yourself
First keep in mind that we are working with quite limited tech. The F3 Multi OLED screen can only display pictures that are in pure bichromatic format (I.E. black and white, not even shades of gray). Couple that with the low resolution of 128x56 per logo and you end up having to compromise on your end result.

You might get a good result on some logos that have a high contrast to begin with, but others like `Bubble Memories` or `Ring Rage` might be more of a challenge.

If you do however get a better result than the one currently on the repository, please consider opening a pull request so we can improve the quality of the library.

### Prepare your image
First thing you need is a Bitmap image file for the logo you want to create. As previously mentioned, the image must be strictly bi-chromatic (**black and white**, not shades of gray) and of a **resolution of 128x56**.

Since white pixels are not displayed, you can fill all the empty spaces with white. Only black pixels will be displayed.

### Get Image Magick
You can get Image Magick from [imagemagick.org](https://imagemagick.org/script/download.php), get the latest version for your OS and install it. Once done you can read the documentation in your favorite shell by typing `magick -usage`

### Make the logo.bin
Using your favorite shell, move to the folder containing your Bitmap image file. Let's assume it is named `logo.bmp`, then run this command :
```magick convert logo.bmp -negate -depth 1 gray:logo.bin```
This will generate a `logo.bin` file compatible with your F3 Multi.

### Place the logo.bin file in your game folder
Simply juste paste the file in the correct game folder, and you will now be able to see your custom logo on your OLED screen.
For example, if you just made a logo for Bubble Memories, place your file in the `bubblem` folder.

## Additional documentation
[Darksoft's official installation guide for the F3 Multi v2](https://www.mediafire.com/file/w15hxgdi69rt1gz/Darksoft+-+F3+Multi+V2+Installation+Guide+v1.pdf/file)

## Licence
Spread this as much as you want, don't make people pay for it. Usual Stuff 👌