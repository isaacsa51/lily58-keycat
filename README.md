# Lily58 Keymap

This is a simple yet somewhat powerful keymap with combos and macros.

<img title="Layout" alt="Layout" src="/res/layout.png">

This SHOULD compile and run with no issues assuming:

* Lily58 Pro
  * Using SEA-PICRO
  * No RGB or underglow of any kind
  * Left-side as `master`

## What does this do?

`keymap.c` is the main file where the configuration is programmed within the macros and OLED display -- if this is undesirable, please use an older commit with the original layout or alter the layout yourself in a fork!

This keymap adds text to the left OLED to show your current layer.

## Layers

**BASE / Colemak**
Basic keymap for typing/overall use with Colemak-DH layout.

**LOWER**
Currently for media usage, navigation with arrow keys and the `SELWORD` macro.

**RAISE**
Planning to rearrange this layout to feature the function keys and mouse functionality.

**SYMBOL**
As the layer says, it's a full layout to feature all the essential symbols without the reach of pressing the numbers.

### Combos

- When pressing `F` & `U` at the same time toggle CAPS LOCK.
- Pressing `X` & `C` at the same time sends a CTRL + C.
  - A macro for Mac is using `X`, `C` + `Backspace` to apply Command + C.
- Pressing `C` & `D` at the same time sends a CTRL + V.
  - A macro for Mac is using `C`, `D` + `Backspace` to apply Command + V.

### Macros

- Currently have a SELWORD keycode to select the entire word of the sentence where the cursor is at.
- `DSKL` and `DSKR` are macros to switch virtual desktop for windows currently.

## TODO

- Add a spotlight macro/combo for Windows & MacOS.
- OS detection.
- Change or improve current macros for each OS.
- Change CTRL/Command keymap depending OS instead of using a different layer.
- Create a GAME keymap.

## Compiling

For the RP2040 controller, you would have to change a few things in the config and rules files. Telling it to compile for the RP2040 and possibly change the naming of the pins used. Docs [here.](https://docs.qmk.fm/#/feature_converters?id=converters)

Command: `qmk compile -e CONVERT_TO=promicro_rp2040 -kb lily58/light -km <username>`

## Flashing

Currently due to my case. I have `BOOTMAGIC_LITE = yes` to press `ESC` before plugging the keyboard to flash the board.
