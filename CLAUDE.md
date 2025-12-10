# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

ZMK firmware configuration for a Corne (3x6 + 3 thumbs) split keyboard with nice!nano v2 controllers. The keyboard supports English/Russian bilingual typing with automatic OS language switching.

## Build Process

Firmware is built via GitHub Actions. Push to the repository triggers the build workflow which uses ZMK's official `build-user-config.yml` action. Download `.uf2` files from the Actions artifacts and flash to each keyboard half.

Build targets are defined in `build.yaml`:
- `nice_nano_v2` + `corne_left`
- `nice_nano_v2` + `corne_right`
- `nice_nano_v2` + `settings_reset` (for clearing bond info)

## Architecture

### Layer System (8 layers, higher number = higher priority)

| Layer | Name | Purpose |
|-------|------|---------|
| 0 | default_layer | English QWERTY base |
| 1 | russian_layer | Russian ЙЦУКЕН (OS language synced) |
| 2 | russian_extra_layer | Extra Russian letters (Ж, Э, Х, Ъ, Ё) + symbols |
| 3 | numpad_layer | Right-hand numpad + left-hand math symbols (Unicode) |
| 4 | symbols_layer | Programming symbols + currency (Unicode) |
| 5 | workspace_layer | Navigation, media, Bluetooth, workspace switching |
| 6 | home_mod_left | Home row mods activated from left thumb |
| 7 | home_mod_right | Home row mods activated from right thumb |

### Language Switching Pattern

The keymap implements bidirectional OS language switching:
- `to_ru` macro: Switches to layer 1 AND sends Alt+Shift (switch OS to Russian)
- `to_en` macro: Switches to layer 0 AND sends Ctrl+Shift (switch OS to English)
- `mo_en_ru`: Momentary layer that temporarily switches OS to English while held
- Russian punctuation keys use macros that: switch to EN → send key → switch back to RU

### Custom Behaviors

Key behaviors in `config/corne.keymap`:
- `tp`: Tap-preferred hold-tap (280ms)
- `hm`: Homerow mods with balanced flavor and idle requirements
- `lt_rev`: Layer-tap with reversed bindings (hold=key, tap=layer)
- `td_base`: Hold=momentary layer, tap=toggle to layer
- `ht_*`: Various hold-tap behaviors for thumb key combinations
- `mm_*`: Mod-morph behaviors for Russian punctuation (normal vs shifted)

### Unicode Input (Linux GTK)

Uses `Ctrl+Shift+U` + hex code + Space pattern for Unicode symbols. Includes:
- Math: ± ≈ ≠ ∞ ≤ ≥ × ÷ √ ∑ ∈ ∅
- Currency: € £ ₽ ₹ ¥
- Typography: « » — № … ° ✓ ✗ ★ ♦

## Key Files

- `config/corne.keymap` - Main keymap with behaviors, macros, and layers
- `config/corne.conf` - Board configuration (Bluetooth, sleep timeout, pointing)
- `build.yaml` - GitHub Actions build matrix
- `LAYOUT.md` - Visual layer documentation (may be outdated)

## Configuration Notes

Bluetooth settings in `corne.conf`:
- TX power: +8 dBm
- Sleep timeout: 1 hour (3600000ms)
- Pointing device support enabled
