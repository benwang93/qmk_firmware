# benwang93 GMMK Pro config

For how to set up QMK MSYS2, fork the repo, set default keyboard and keymap, create new keymap, see <https://docs.qmk.fm/newbs>.

With this config, the keyboard can be put into DFU by pressing Fn + backslash (\)

## Updating layout

Changes to the layout are made via the QMK configurator online.

1. Go to <https://config.qmk.fm/>
2. Upload the latest JSON
3. Make changes using the configurator
4. Download the JSON and update the one in this repo
5. Generate new C-code for `keymap.c` by running `qmk json2c keyboards/gmmk/pro/rev1/ansi/keymaps/benwang93/gmmk_pro_rev1_ansi_benwang93.json`
6. Copy the `keymaps` array definition to `keymap.c`
7. If new layers are added, update `keymap.c`'s `encoder_map` so that it has the same number of entries as there are layers in the `keymaps` array.
8. See **Building firmware** for how to build

## Building firmware

Build with the following:

```{bash}
qmk compile -kb gmmk/pro/rev1/ansi -km benwang93
```

If you've set the defaults (see `qmk config`), then simply run `qmk compile`.

## Flashing firmware

See Glorious's documentation at <https://www.gloriousgaming.com/blogs/resources/step-by-step-guide-to-configuring-your-gmmk-pro-using-qmk>
