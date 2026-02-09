# QMK Keebio Iris CE Configuration

This repository contains the QMK firmware configuration for a Keebio Iris CE keyboard with a custom keymap optimized for German language support and advanced text processing features.

## Keymap Overview

The keymap consists of 7 layers with a Colemak base layout, homerow mods, and advanced "magic key" functionality for text expansion:

### Layer 0: Base (COLEMAK)

The primary typing layer featuring:
- Colemak letter layout (Q-W-F-P-G / J-L-U-Y on top row)
- Homerow mods on S (Alt), T (Brackets Layer), D (GUI) on left hand
- Homerow mods on H (GUI), N (Brackets Layer), E (Ctrl) on right hand
- Top row layer triggers on F (Special), P (Media), L (Media)
- Tab key: Tap dance (Tab / Shift+Tab)
- Space key: Tap dance (Space / Tab)
- German locale support (DE_COMM, DE_DOT, etc.)
- Magic keys for text expansion and shortcuts

**Layout:**
```
┌──────┬─────┬─────┬─────┬─────┬─────┐                    ┌─────┬─────┬─────┬─────┬─────┬──────┐
│ ESC  │  1  │  2  │  3  │  4  │  5  │                    │  6  │  7  │  8  │  9  │  0  │ BSPC │
├──────┼─────┼─────┼─────┼─────┼─────┤                    ├─────┼─────┼─────┼─────┼─────┼──────┤
│MagTab│  Q  │  W  │ F/7 │ P/6 │  G  │                    │  J  │ L/6 │  U  │  Y  │     │      │
├──────┼─────┼─────┼─────┼─────┼─────┤                    ├─────┼─────┼─────┼─────┼─────┼──────┤
│ CTRL │  A  │  R  │S/Alt│ T/4 │ D/G │                    │ H/G │ N/4 │ E/C │  I  │  O  │ ENTR │
├──────┼─────┼─────┼─────┼─────┼─────┼──────┐    ┌──────┼─────┼─────┼─────┼─────┼─────┼──────┤
│ SHFT │  Z  │  X  │  C  │  V  │  B  │ HOME │    │ END  │  K  │  M  │  ,  │  .  │  /  │ CAPW │
└──────┴─────┴─────┴─────┼─────┼─────┼──────┤    ├──────┼─────┼─────┼─────┴─────┴─────┴──────┘
                          │BSPC │NAV/M│SPC/T │    │ SHFT │XTR/M│ ENTR│
                          └─────┴─────┴──────┘    └──────┴─────┴─────┘
```
*Legend:*
- *MagTab* = Tap Tab or double-tap Shift+Tab
- *S/Alt* = Hold Alt
- *T/4* = Layer 4 (Brackets)
- *D/G* = Hold GUI/Win
- *F/7* = Layer 7 (Special)
- *P/6* = Layer 6 (Media)
- *L/6* = Layer 6 (Media)
- *SPC/T* = Tap Space or double-tap Tab
- *NAV/M* = Tap for Navigation layer or hold for Left Magic
- *XTR/M* = Tap for Extra layer or hold for Right Magic
- *CAPW* = Caps Word toggle

**Combos:**
- G+A+M+E = Switch to Game layer

### Layer 1: Game (GAME)

Gaming-optimized layer with standard QWERTY-like layout:
- Removes homerow mods for easier gaming
- Standard WASD positioning
- Easy access to numbers and common gaming keys
- Return to Colemak via dedicated keys

**Layout:**
```
┌──────┬─────┬─────┬─────┬─────┬─────┐                    ┌─────┬─────┬─────┬─────┬─────┬──────┐
│ ESC  │  1  │  2  │  3  │  4  │  5  │                    │  6  │  7  │  8  │  9  │  0  │ BSPC │
├──────┼─────┼─────┼─────┼─────┼─────┤                    ├─────┼─────┼─────┼─────┼─────┼──────┤
│ TAB  │  Q  │  W  │  F  │  P  │  G  │                    │  J  │  L  │  U  │  Y  │     │      │
├──────┼─────┼─────┼─────┼─────┼─────┤                    ├─────┼─────┼─────┼─────┼─────┼──────┤
│ CTRL │  A  │  R  │  S  │  T  │  D  │                    │  H  │  N  │  E  │  I  │  O  │ ENTR │
├──────┼─────┼─────┼─────┼─────┼─────┼──────┐    ┌──────┼─────┼─────┼─────┼─────┼─────┼──────┤
│ SHFT │  Z  │  X  │  C  │  V  │  B  │ HOME │    │ END  │  K  │  M  │  ,  │  .  │  /  │ CAPS │
└──────┴─────┴─────┴─────┼─────┼─────┼──────┤    ├──────┼─────┼─────┼─────┴─────┴─────┴──────┘
                          │ COL │ NAV │BRC/SP│    │ SHFT │ XTRA│ COL │
                          └─────┴─────┴──────┘    └──────┴─────┴─────┘
```
*Legend: COL = Return to Colemak layer, BRC/SP = Brackets layer or Space*

### Layer 2: Navigation & Numbers (NAVIGATION)

Navigation and number pad layer:
- Arrow keys and page navigation on left side
- Number pad (0-9) on right side
- Function row access
- Bootloader access

**Layout:**
```
┌──────┬─────┬─────┬─────┬─────┬─────┐                    ┌─────┬─────┬─────┬─────┬─────┬──────┐
│      │     │     │     │     │ BOOT│                    │     │     │     │     │     │      │
├──────┼─────┼─────┼─────┼─────┼─────┤                    ├─────┼─────┼─────┼─────┼─────┼──────┤
│      │     │PgDn │  ↑  │PgUp │     │                    │     │  7  │  8  │  9  │  0  │ PgDn │
├──────┼─────┼─────┼─────┼─────┼─────┤                    ├─────┼─────┼─────┼─────┼─────┼──────┤
│      │HOME │  ←  │  ↓  │  →  │ END │                    │  }  │  4  │  5  │  6  │  +  │  |   │
├──────┼─────┼─────┼─────┼─────┼─────┼──────┐    ┌──────┼─────┼─────┼─────┼─────┼─────┼──────┤
│      │     │     │     │     │     │ TO 0 │    │      │  ]  │  1  │  2  │  3  │  ß  │      │
└──────┴─────┴─────┴─────┼─────┼─────┼──────┤    ├──────┼─────┼─────┼─────┴─────┴─────┴──────┘
                          │     │     │ DEL  │    │ DEL  │     │  0  │
                          └─────┴─────┴──────┘    └──────┴─────┴─────┘
```

### Layer 3: Brackets (BRACKETS)

Dedicated layer for brackets, parentheses, and function keys:
- All bracket types: (), [], {}, <, >
- F1-F12 function keys on top row
- OS-specific bracket implementation for cross-platform compatibility

**Layout:**
```
┌──────┬─────┬─────┬─────┬─────┬─────┐                    ┌─────┬─────┬─────┬─────┬─────┬──────┐
│ F12  │ F1  │ F2  │ F3  │ F4  │ F5  │                    │ F6  │ F7  │ F8  │ F9  │ F10 │ F11  │
├──────┼─────┼─────┼─────┼─────┼─────┤                    ├─────┼─────┼─────┼─────┼─────┼──────┤
│      │     │     │     │  <  │     │                    │     │  >  │     │     │     │ BOOT │
├──────┼─────┼─────┼─────┼─────┼─────┤                    ├─────┼─────┼─────┼─────┼─────┼──────┤
│      │     │  {  │  [  │  (  │     │                    │     │  )  │  ]  │  }  │     │      │
├──────┼─────┼─────┼─────┼─────┼─────┼──────┐    ┌──────┼─────┼─────┼─────┼─────┼─────┼──────┤
│      │     │     │     │     │     │ TO 0 │    │      │     │     │     │     │     │      │
└──────┴─────┴─────┴─────┼─────┼─────┼──────┤    ├──────┼─────┼─────┼─────┴─────┴─────┴──────┘
                          │     │     │ SPC  │    │ ENTR │AREP │     │
                          └─────┴─────┴──────┘    └──────┴─────┴─────┘
```
*Legend: AREP = Alternate Repeat*

### Layer 4: Symbols (EXTRA)

German keyboard symbols and special characters:
- German-specific characters: ä, ö, ü, ß, €, §
- Mathematical and punctuation symbols
- Special characters with backslash and pipe

**Layout:**
```
┌──────┬─────┬─────┬─────┬─────┬─────┐                    ┌─────┬─────┬─────┬─────┬─────┬──────┐
│      │     │     │     │     │ BOOT│                    │     │     │     │     │     │      │
├──────┼─────┼─────┼─────┼─────┼─────┤                    ├─────┼─────┼─────┼─────┼─────┼──────┤
│      │     │  `  │  ~  │  +  │  §  │                    │     │  \  │  }  │     │     │      │
├──────┼─────┼─────┼─────┼─────┼─────┤                    ├─────┼─────┼─────┼─────┼─────┼──────┤
│      │  =  │  %  │  !  │  "  │  $  │                    │  &  │  /  │  ?  │  #  │  |  │      │
├──────┼─────┼─────┼─────┼─────┼─────┼──────┐    ┌──────┼─────┼─────┼─────┼─────┼─────┼──────┤
│      │  ä  │  ö  │  ü  │  |  │  €  │ TO 0 │    │      │     │  \  │     │     │  |  │      │
└──────┴─────┴─────┴─────┼─────┼─────┼──────┤    ├──────┼─────┼─────┼─────┴─────┴─────┴──────┘
                          │     │     │      │    │      │     │     │
                          └─────┴─────┴──────┘    └──────┴─────┴─────┘
```

### Layer 5: Media (MEDIA)

Media controls and RGB matrix settings:
- Media playback controls (play, pause, stop, next, previous)
- Volume controls
- RGB matrix controls (toggle, mode, hue, saturation, value, speed)

**Layout:**
```
┌──────┬─────┬─────┬─────┬─────┬─────┐                    ┌─────┬─────┬─────┬─────┬─────┬──────┐
│      │     │     │     │     │     │                    │     │     │     │     │     │      │
├──────┼─────┼─────┼─────┼─────┼─────┤                    ├─────┼─────┼─────┼─────┼─────┼──────┤
│      │     │MUTE │STOP │VOL+ │     │                    │     │     │     │     │RGBTG│      │
├──────┼─────┼─────┼─────┼─────┼─────┤                    ├─────┼─────┼─────┼─────┼─────┼──────┤
│      │     │PREV │PLAY │NEXT │     │                    │     │RGBM+│RGB+ │HUE+ │SPD+ │      │
├──────┼─────┼─────┼─────┼─────┼─────┼──────┐    ┌──────┼─────┼─────┼─────┼─────┼─────┼──────┤
│      │     │     │     │VOL- │     │ TO 0 │    │      │     │RGBM-│RGB- │HUE- │SPD- │      │
└──────┴─────┴─────┴─────┼─────┼─────┼──────┤    ├──────┼─────┼─────┼─────┴─────┴─────┴──────┘
                          │     │     │      │    │      │     │     │
                          └─────┴─────┴──────┘    └──────┴─────┴─────┘
```

### Layer 6: Special (SPECIAL)

System shortcuts and special functions:
- Copy, Paste, Cut operations
- OS-specific Reload command (Cmd+R on macOS, Ctrl+R on Windows/Linux)

**Layout:**
```
┌──────┬─────┬─────┬─────┬─────┬─────┐                    ┌─────┬─────┬─────┬─────┬─────┬──────┐
│      │     │     │     │     │     │                    │     │     │     │     │     │      │
├──────┼─────┼─────┼─────┼─────┼─────┤                    ├─────┼─────┼─────┼─────┼─────┼──────┤
│      │     │     │     │     │     │                    │     │     │     │     │     │      │
├──────┼─────┼─────┼─────┼─────┼─────┤                    ├─────┼─────┼─────┼─────┼─────┼──────┤
│      │     │     │PASTE│COPY │ CUT │                    │     │RELOD│     │     │     │      │
├──────┼─────┼─────┼─────┼─────┼─────┼──────┐    ┌──────┼─────┼─────┼─────┼─────┼─────┼──────┤
│      │     │     │     │     │     │ TO 0 │    │      │     │     │     │     │     │      │
└──────┴─────┴─────┴─────┼─────┼─────┼──────┤    ├──────┼─────┼─────┼─────┴─────┴─────┴──────┘
                          │     │     │      │    │      │     │     │
                          └─────┴─────┴──────┘    └──────┴─────┴─────┘
```

## Special Features

### Homerow Mods

The keymap uses homerow modifications for ergonomic access to modifier keys:
- **Left hand:** Alt (S), Layer 4/Brackets (T), GUI/Win (D)
- **Right hand:** GUI/Win (H), Layer 4/Brackets (N), Ctrl (E)
- Configured with per-key tapping term

### Top Row Layers

Additional layer access via top row hold:
- **F key:** Special layer (Layer 7) with copy/paste/cut shortcuts
- **P key:** Media layer (Layer 6) for media controls
- **L key:** Media layer (Layer 6) for media controls

### Tap Dances

- **Tab key:** Single tap = Tab, Double tap = Shift+Tab
- **Space key:** Single tap = Space, Double tap = Tab
- **Navigation/Left Magic:** Tap for Navigation layer, Hold for Left Magic functionality
- **Extra/Right Magic:** Tap for Extra layer, Hold for Right Magic functionality

### Magic Keys

The keymap includes advanced "magic key" functionality for text expansion and shortcuts:

#### Left Magic (LMAGIC)
Activated by holding the Navigation layer thumb key, provides text expansion based on the last key pressed:
- **F** → "unction" (e.g., f+magic = function)
- **I** → "on" (e.g., i+magic = ion)
- **T** → "he" (e.g., t+magic = the)
- **T** (after "re") → "urn" (e.g., ret+magic = return)
- **.** → ".." (double period)
- Plus single character completions for L, E, M, N, O, U

#### Right Magic (RMAGIC)
Activated by holding the Extra layer thumb key, provides:

**Replacement mode:**
- **AE** → ä (e.g., ae+magic = ä)
- **OE** → ö (e.g., oe+magic = ö)
- **UE** → ü (e.g., ue+magic = ü)

**Addition mode:**
- **E** → "nt" (e.g., e+magic = ent)
- **I** → "ng" (e.g., i+magic = ing)
- **M** → "ent" (e.g., m+magic = ment)
- Plus single character completions for A, B, C, D, F, G, P, R, S, T, W, Z

### OS Detection

The keymap uses QMK's OS detection to provide platform-specific behavior:
- **Brackets:** Automatically sends correct keycodes for {, }, [, ], | on macOS vs Windows/Linux
- **Reload command:** Sends Cmd+R on macOS/iOS, Ctrl+R on Windows/Linux

### Combos

- **G+A+M+E combo:** Activates the Game layer for gaming mode
- **T+N combo (disabled):** Caps Word toggle (currently commented out)

### Caps Word

Activated via dedicated key on base layer, continues through minus and backspace for easy constant/variable naming.

### Repeat Key

QMK's Repeat Key feature is enabled, with an alternate repeat key on the Brackets layer for advanced text editing.

## RGB Matrix

The keyboard features RGB matrix lighting with:
- Default mode: `RGB_MATRIX_SOLID_REACTIVE_WIDE` (purple hue)
- Game layer mode: `RGB_MATRIX_BAND_SAT`
- Full control via Media layer (toggle, mode change, hue, saturation, value, speed)

## Building

This keymap requires QMK firmware. Build and flash using:

```bash
qmk compile -kb keebio/iris_ce -km adelholtz
qmk flash -kb keebio/iris_ce -km adelholtz
```

Or from the QMK firmware directory:

```bash
make keebio/iris_ce:adelholtz
make keebio/iris_ce:adelholtz:flash
```

## Features Enabled

The following QMK features are enabled in `rules.mk`:
- `TRI_LAYER_ENABLE` - Tri-layer support
- `REPEAT_KEY_ENABLE` - Repeat key functionality
- `COMBO_ENABLE` - Key combinations
- `TAP_DANCE_ENABLE` - Tap dance keys
- `CAPS_WORD_ENABLE` - Caps word feature
- `OS_DETECTION_ENABLE` - OS-specific behavior

## German Keyboard Support

This keymap uses German locale (`keymap_german.h`) for proper character mapping including:
- Umlauts: ä, ö, ü
- Special characters: ß, €, §, °
- German-specific symbols and punctuation
- OS-aware bracket handling for cross-platform compatibility

## File Structure

- `keymap.c` - Main keymap file with layer definitions and custom keycodes
- `adelholtz.h` - Header with custom keycode definitions and enums
- `layer_layout.c` - Layer layout definitions
- `magic.c` - Left and Right Magic key implementation
- `tap_dance.c` - Tap dance behavior definitions
- `combos.c` - Combo definitions
- `rgb_layer_state.c` - RGB matrix layer state handling
- `rules.mk` - Feature flags and build configuration
