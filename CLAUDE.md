# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Overview

This is a ZMK (Zephyr-based Mechanical Keyboard) firmware configuration for a Corneish Zen v2 split keyboard. The repository uses GitHub Actions to automatically build firmware when changes are pushed.

## Key Files and Structure

- `build.yaml`: Defines the keyboard boards to build (corneish_zen_v2_left and corneish_zen_v2_right)
- `config/corneish_zen.conf`: Hardware configuration settings (display, sleep timeout, mouse support)
- `config/corneish_zen.keymap`: Main keymap definition with all layers and key bindings
- `config/west.yml`: ZMK framework configuration using a custom branch with mouse support

## Layers

The keyboard uses 6 layers:
- **QWERTY** (0): Base typing layer
- **NAV** (1): Navigation and window management
- **MEDIABT** (2): Media controls and Bluetooth settings
- **SYMBOL** (3): Symbols and special characters
- **NUMBER** (4): Number pad and math operators
- **MOUSE** (5): Mouse movement and scrolling

## Common Development Tasks

### Building Firmware
The firmware is automatically built via GitHub Actions when changes are pushed to the repository. Check the Actions tab for build status and to download firmware artifacts.

### Modifying Keymaps
Edit `config/corneish_zen.keymap` to change key bindings. The file uses:
- Layer definitions with `#define` statements
- Custom behaviors for tap-dance, hold-tap, and mod-tap keys
- ASCII art comments showing the visual layout

### Adding New Behaviors
Custom behaviors are defined in the `/behaviors` block in the keymap file. Examples include:
- `tap_dance`: Multiple actions on successive taps
- `hold-tap`: Different actions for tap vs hold
- `mod_sticky_key`: Sticky modifier keys

## Technical Notes

- Uses a custom ZMK branch (`caksoylar/zen-v2+mouse`) for mouse support
- Display is configured for white-on-black with periodic refresh
- Supports both 6-column and 5-column layouts (currently using 6-column)
- Mouse acceleration and scroll speed are configured in the keymap
