# Corne Keyboard Layout

**Hardware:** Corne (3x6 + 3 thumbs split)
**Controller:** nice!nano v2
**Firmware:** ZMK

---

## Layer 0: DEFAULT (Base QWERTY)

```
┌─────┬───┬───┬───┬───┬───┐                 ┌───┬───┬───┬───┬───┬─────┐
│ TAB │ Q │ W │ E │ R │ T │                 │ Y │ U │ I │ O │ P │ ESC │
├─────┼───┼───┼───┼───┼───┤                 ├───┼───┼───┼───┼───┼─────┤
│CTRL │ A │ S │ D │ F │ G │                 │ H │ J │ K │ L │ ; │ '/L1│
├─────┼───┼───┼───┼───┼───┤                 ├───┼───┼───┼───┼───┼─────┤
│SHFT │ Z │ X │ C │ V │ B │                 │ N │ M │ , │ . │ / │SHIFT│
└─────┴───┴───┼───┼───┼───┤                 ├───┼───┼───┼───┴───┴─────┘
              │GUI│ L1│A/E│                 │H/S│BSP│ L2│
              └───┴───┴───┘                 └───┴───┴───┘
```

**Special Keys:**
- `'/L1` = Layer-tap: Hold for Layer 1, Tap for `'` (quote)
- `A/E` = Tap-preferred: Alt or Enter
- `H/S` = Tap-preferred: Hyper (Ctrl+Shift+Alt+GUI) or Space
- `L1` = Momentary Layer 1
- `L2` = Momentary Layer 2

---

## Layer 1: LOWER (Numbers & Symbols)

```
┌─────┬───┬───┬───┬───┬───┐                 ┌───┬───┬───┬───┬───┬─────┐
│     │ ! │ @ │ # │ $ │ % │                 │ ^ │ & │ * │ ( │ ) │  \  │
├─────┼───┼───┼───┼───┼───┤                 ├───┼───┼───┼───┼───┼─────┤
│     │ 1 │ 2 │ 3 │ 4 │ 5 │                 │ - │ = │ ` │ [ │ ] │  |  │
├─────┼───┼───┼───┼───┼───┤                 ├───┼───┼───┼───┼───┼─────┤
│SHFT │ 6 │ 7 │ 8 │ 9 │ 0 │                 │ _ │ + │ ~ │ { │ } │SHIFT│
└─────┴───┴───┼───┼───┼───┤                 ├───┼───┼───┼───┴───┴─────┘
              │GUI│   │A/E│                 │H/S│BSP│   │
              └───┴───┴───┘                 └───┴───┴───┘
```

---

## Layer 2: RAISE (Function Keys, Media, Bluetooth)

```
┌─────┬─────┬─────┬─────┬─────┬─────┐       ┌───┬───┬───┬───┬────┬───────┐
│     │ F1  │ F2  │ F3  │ F4  │ F5  │       │F6 │F7 │F8 │F9 │F10 │STUDIO │
├─────┼─────┼─────┼─────┼─────┼─────┤       ├───┼───┼───┼───┼────┼───────┤
│     │Prev │Next │Vol -│Vol +│Play │       │ ← │ ↓ │ ↑ │ → │    │       │
├─────┼─────┼─────┼─────┼─────┼─────┤       ├───┼───┼───┼───┼────┼───────┤
│BTCLR│ BT1 │ BT2 │ BT3 │ BT4 │ BT5 │       │   │   │   │   │    │       │
└─────┴─────┴─────┼─────┼─────┼─────┤       ├───┼───┼───┼───┴────┴───────┘
                  │     │     │     │       │   │   │   │
                  └─────┴─────┴─────┘       └───┴───┴───┘
```

**Bluetooth Keys:**
- `BTCLR` = Clear all Bluetooth pairings
- `BT1-5` = Select Bluetooth profile 1-5

**Media Keys:**
- `Prev/Next` = Previous/Next track
- `Vol +/-` = Volume up/down
- `Play` = Play/Pause

---

## Issues to Fix

1. ✅ **FIXED:** Changed from jorne to corne shields
2. ⚠️ **TODO:** Remove Studio references from keymap (line 10, line 63)
3. ⚠️ **TODO:** Rename `jorne.keymap` → `corne.keymap`
4. ⚠️ **TODO:** Rename `jorne.conf` → `corne.conf`
5. ⚠️ **TODO:** Remove `CONFIG_ZMK_STUDIO=y` from config

---

## Next Steps

Ready to customize the layout? Common changes:
- Add/remove layers
- Change key positions
- Add combos (chord keys)
- Modify tap/hold timing
- Add mouse keys
- Configure RGB (if available)
