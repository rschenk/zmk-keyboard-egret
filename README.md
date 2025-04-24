# Egret ZMK Module

This is a [ZMK Module](https://zmk.dev/docs/features/modules) for my [Egret keyboard](https://github.com/rschenk/egret).

To use this in your zmk-config, follow the [ZMK Module docs](https://zmk.dev/docs/features/modules) using the config below. You'll name your keymap `egret.keymap`.

## Usage

Add the following entries to `remotes` and `projects` in `config/west.yml`

```yaml
# config/west.yml
manifest:
  remotes:
    - name: zmkfirmware
      url-base: https://github.com/zmkfirmware
    - name: rschenk
      url-base: https://github.com/rschenk
  projects:
    - name: zmk
      remote: zmkfirmware
      import: app/west.yml
    - name: zmk-keyboard-egret
      remote: rschenk
      revision: main
  self:
    path: config
```

And then in your `build.yaml` file:

```yaml
# build.yaml
board: ["nice_nano_v2"]
shield: ["egret"]
```
