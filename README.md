# Lily58 Kiry Pet + WPM Counter
This is a combination of the default Lily58 layout / configs / etc combined with https://github.com/Rwarcards762/lily58_bongocat.

<img title="Layout" alt="Layout" src="/res/layout.png">

This SHOULD compile and run with no issues assuming:

- Lily58 Pro
  - Using SEA-PICRO _or replica microcontroller that need to flash with `.uf2`_
  - No RGB or underglow of any kind
  - Left-side as `master`

## Inside this `kiry_cat` branch

Coded and implemented a cat pet to show sleep/awake and running animations depending the WPM calculated. Got all the inspiration from Luna the pet from this [repo from HellTM.](https://github.com/HellSingCoder/qmk_firmware/tree/master/keyboards/sofle/keymaps/helltm)

This keymap adds to the left OLED Mac and Windows logo to identify on which position the mod keys are, CAPS LOCK indicator & layers which are:

- Colemak
- Qwerty
- Games
- Mac
- Raise
- Lower

With the company of Kiry, my beloved cat that animates when pressing CTRL, CAPS and jumps when pressing space!

<img title="Animations" alt="Animations" src="/res/animations_kiry.png">

On the right OLED shows the WPM count and an unofficial Lily58 logo on the upper right screen to populate the screen.

## What does this do?

`keymap.c` in a previous commit used the original layout -- utilize that if desired. Keep in mind the different branches that exist in this repo -- if this is undesirable, please use an older commit with the original layout or alter the layout yourself in a fork!



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
