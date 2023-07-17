# Lily58 BongoCat + WPM + Layer Indicator

This is a combination of the default Lily58 layout / configs / etc combined with https://github.com/Rwarcards762/lily58_bongocat.

<img title="Layout" alt="Layout" src="/res/layout.png">

This SHOULD compile and run with no issues assuming:

- Lily58 Pro
  - Using SEA-PICRO _or replica microcontroller that need to flash with `.uf2`_
  - No RGB or underglow of any kind
  - Left-side as `master`

## Inside this `luna_pet` branch

Ported Luna the pet into my Lily58. [Repo of HellTM.](https://github.com/HellSingCoder/qmk_firmware/tree/master/keyboards/sofle/keymaps/helltm)

**Keep in mind that I just ported the OLED functionality into the keymap, code and layout may be deprecated.**
## What does this do?

~~`keymap.c` in a previous commit used the original layout -- utilize that if desired. Keep in mind the different branches that exist in this repo -- if this is undesirable, please use an older commit with the original layout or alter the layout yourself in a fork!~~



~~This keymap adds text to the left OLED to show your current estimated WPM, as well as what layer you are on.~~

~~This keymap adds a Bongo Cat animation loop on the right OLED:~~

~~- At below 30WPM, Bongo Cat idles.~~
~~- At 30 WPM, Bongo Cat raises its arms.~~
~~- At 40+ WPM, Bongo Cat hits the table in a looping animation.~~

Currently, there are 3 different branches in this repo, they are the same layouts but different OLED display functionality.

- `main`
- `kiry_cat`
- `luna_pet`

Each one represents what the OLED screen shows and each `README.md` explains the differences. 

_**Maybe adding more branches to test keyboard layouts in the future.**_

*Please note that the "WPM" counter is more for fun than for getting realistic WPM numbers from.*

## Extras

- Pressing the Right and Left Shift at the same time activates the COMBO to press CAPS LOCK.
- Macro as `SELWORD` to select the entire word where the cursor is at.
- Tapping twice the `LOWER` & `RAISE` toggles them.

## TODO

- In any layer that isn't the `BASE` one, `RAISE` & `LOWER` can't be activated.
- Currently, the left OLED falls asleep on its own, and the timeout does not match that of the right side An end goal would be to have these sides sleep together and wake together.
- Detection of which OS is currently connected to and be able to re-arrange the modifiers keys is still missing.
- Implement corne MOD key indicators from 
- Implement macros to put (<cursor>), [<cursor>], {<cursor>} like any IDE.

- Currently, the left OLED falls asleep on its own, and the timeout does not match that of the right side. An end goal would be to have these sides sleep together and wake together.

## Compiling

For the RP2040 controller, you would have to change a few things in the config and rules files. Telling it to compile for the RP2040 and possibly change the naming of the pins used. Docs [here.](https://docs.qmk.fm/#/feature_converters?id=converters)

Command: `qmk compile -e CONVERT_TO=promicro_rp2040 -kb lily58/light -km <username>`