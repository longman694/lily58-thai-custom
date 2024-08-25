This repository hosts a QMK configuration tailored for the Lily58 keyboard, enhancing its compatibility with the Thai language. 

Recognizing that compact layouts such as 40% keyboards lack the space to accommodate all essential Thai characters, this project advocates for a minimum of 4 rows and 12 columns. Consequently, [the Lily58](https://github.com/kata0510/Lily58), with its split design, emerges as an ideal choice. 

To improve Thai language compatibility, the keymapping has been positioning 'ข' and 'ช' characters on the accessible upper right keys, while the less used 'ฃ/ฅ' are nested within a secondary layer beneath the 'ช' key.

# Feature

- Full Thai keys support.
- Support real-time config with [VIA](https://usevia.app/)
- N keys rollover
- Mouse and media keys support.
- Minimal design with no LED and RGB (for now)

# Build from scratch

## Dependency

- [QMK CLI](https://docs.qmk.fm/cli)

```
python3 -m pip install qmk
export QMK_HOME='~/qmk_firmware' # Optional, set the location for `qmk_firmware`
qmk setup  # This will clone `qmk/qmk_firmware` and optionally set up your build environment
```

## compile

1. copy the keymap

```
cp -r keymaps/thai ~/qmk_firmware/keyboards/lily58/keymaps/
```

2. (optional) convert config into keymap

```
qmk json2c lily58_rev1_thai.json > ~/qmk_firmware/keyboards/lily58/keymaps/thai/keymap.c
```

3. compile

```
qmk compile -kb lily58/rev1 -km thai
```

4. flash `.hex` file into both sides of the keyboard with [QMK Toolbox](https://qmk.fm/toolbox) and assign right-side to EEPROM.


## DEBUG

For Pro Micro ver Elite-C Rev.3 (Pro Micro USB type-C), there is a problem with VBUS, 
so it cannot determine which size is MASTER and the right half keyboard will not work.
To handle this problem, this project uses `EE_HAND` and flashes a configuration to EEPROM directly.
