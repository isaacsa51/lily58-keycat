# Lily58 BongoCat + WPM + Layer Indicator

This is a combination of the default Lily58 layout / configs / etc combined with https://github.com/jordi-7/qmk_firmware/tree/master/keyboards/lily58/keymaps/jgr.

<img title="Layout" alt="Layout" src="/res/layout.png">

I could not get their version working but managed to adapt their code in with a default layout to eventually achieve a working product.

This SHOULD compile and run with no issues assuming:

* Lily58 Pro
  * Using SEA-PICRO
  * No RGB or underglow of any kind
  * Left-side as `master`

## What does this do?

`keymap.c` is the main file where the configuration is programmed within the macros and OLED display -- if this is undesirable, please use an older commit with the original layout or alter the layout yourself in a fork!

This keymap adds text to the left OLED to show your current estimated WPM, as well as what layer you are on.

This keymap adds a Bongo Cat animation loop on the right OLED:

* At below 30WPM, Bongo Cat idles.
* At 30 WPM, Bongo Cat raises its arms...
* At 40+ WPM, Bongo Cat hits the table in a looping animation.

*Please note that the "WPM" counter is more for fun than for getting realistic WPM numbers from.*

## TODO

- Currently, the left OLED falls asleep on its own, and the timeout does not match that of the right side. An end goal would be to have these sides sleep together and wake together.
- Leader key acros still missing.
- Detection of which OS is currently connected to and be able to re-arrange the modifiers keys is still missing.

## Compiling

For the RP2040 controller, you would have to change a few things in the config and rules files. Telling it to compile for the RP2040 and possibly change the naming of the pins used. Docs [here.](https://docs.qmk.fm/#/feature_converters?id=converters)

Command: `qmk compile -e CONVERT_TO=promicro_rp2040 -kb lily58/light -km <username>`
