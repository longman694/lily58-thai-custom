QMK config for lily58 keyboard optimized for Thai language.


# Dependency

- [QMK CLI](https://docs.qmk.fm/cli)


# compile


1. New keymap

```
qmk new-keymap -kb lily58
```

2. convert config into keymap

```
qmk json2c lily58_rev1_thai.json > <keymap directory>/keymap.c
```

3. compile

```
qmk compile -kb lily58/rev1 -km <you keymap name>
```

4. flash .hex file into both side of the keyboard with [QMK Toolbox](https://qmk.fm/toolbox) or CLI


