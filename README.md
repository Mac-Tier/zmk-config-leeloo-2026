# Leeloo ZMK Configuration

This repository provides the ZMK configuration and GitHub Actions build setup for Clickety Split Leeloo v2.1 (Rev3) using the Chiisai controller.

It is intended to be used as a GitHub template repository. You do not need to maintain a local ZMK source tree to customize and build your firmware.

## Getting Started

1. Create your own repository from this template.
2. Edit:

   `config/clickety_split_leeloo.keymap`

3. Commit and push your changes.
4. Open the **Actions** tab in GitHub.
5. Open the latest successful **Build ZMK firmware** run.
6. Download the `leeloo-firmware` artifact.

The downloaded artifact contains:

- `leeloo-left.uf2`
- `leeloo-right.uf2`
- `leeloo-settings-reset.uf2`

Flash the left and right firmware files to their corresponding halves.

## Customizing the Keymap

Most users only need to edit:

`config/clickety_split_leeloo.keymap`

The supplied keymap includes:

- QWERTY
- Lower
- Raise
- Bluetooth profile controls
- RGB controls
- encoder volume control
- bootloader and reset controls

## Hardware Revision

This template builds Clickety Split Leeloo v2.1 (Rev3) with Chiisai by default.

Earlier supported Leeloo revisions can also be configured, but may require different build targets or controller settings.

The current default shields are:

- `clickety_split_leeloo_rev3_left`
- `clickety_split_leeloo_rev3_right`

## Settings Reset

`leeloo-settings-reset.uf2` clears stored ZMK settings from a controller.

After flashing the settings-reset firmware, flash the normal left or right firmware again before using the keyboard.

## Firmware Versions

This configuration intentionally pins known-good revisions of both ZMK and the Clickety Split hardware module.

Dependency revisions are defined in:

`config/west.yml`

The GitHub Actions workflow is pinned to the matching ZMK revision.

This keeps firmware builds reproducible and prevents an upstream update from unexpectedly changing a working configuration.

## Hardware Support

This template is intended for Clickety Split Leeloo v2.1 (Rev3) using the Chiisai controller.

Board, shield, display, RGB, split, encoder, and power-management definitions are provided by the Clickety Split ZMK hardware module:

`ClicketySplit/zmk-clickety-split`

Hardware-specific configuration should normally remain in that module rather than being duplicated in this repository.

## Files

    .github/workflows/build.yml
    build.yaml
    config/
    ├── clickety_split_leeloo.conf
    ├── clickety_split_leeloo.keymap
    └── west.yml

## License

See `LICENSE`.
