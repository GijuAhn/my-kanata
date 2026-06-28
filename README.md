# my-kanata

> A single-layer-first keyboard layout optimized for programming and writing.

## Why This Layout

- Mnemonic keys reduce lookup cost.
- Editing and navigation stay near the home row.
- Left hand edits. Right hand navigates.
- Timing-sensitive behavior is limited to `Space`/Shift/RAlt tap-hold and base-layer combos.

## Quick Map

| Area                 | Behavior                                                   |
| -------------------- | ---------------------------------------------------------- |
| Base typing          | QWERTY-style typing, with `CapsLock` mapped to `Left Ctrl` |
| `Space` tap          | Normal Space                                               |
| `Space` hold         | Momentary `SpaceFn` layer                                  |
| Left-hand `SpaceFn`  | Delete, backspace, select line, copy, paste                |
| Right-hand `SpaceFn` | Home, End, arrows, Page Up/Down, app switching             |
| Base combos          | Undo, cut, copy, paste, volume control                     |
| Safety rule          | Base combos are disabled inside `SpaceFn`                  |

## Files

| Path                       | Purpose                                            |
| -------------------------- | -------------------------------------------------- |
| `src/kanata.kbd`           | Runtime config loaded by Kanata                    |
| `assets/kanata_core.kbd`   | Core reference copy                                |
| `assets/kanata_expand.kbd` | Expanded backup with unused or experimental layers |

## Diagram Guide

The compact diagrams follow a Leopold FC660M-style physical layout.
Labels are shortened to keep the README readable on GitHub.

## Base Layer

The base layer stays close to QWERTY, with a few tap-hold edits:

- `CapsLock` acts as `Left Ctrl`.
- The physical `Insert` key {selects the current line}: `Home`, then `Shift+End`.
- Left/Right Shift tap `(`/`)` and hold as Shift.
- Right Alt taps as RAlt and holds as Shift.

```text
+-----+-----+-----+-----+-----+-----+-----+-----+-----+-----+-----+-----+-----+-------+ +-----+
|  `  |  1  |  2  |  3  |  4  |  5  |  6  |  7  |  8  |  9  |  0  |  -  |  =  | Bspc  | |SelLn|
+-----+-----+-----+-----+-----+-----+-----+-----+-----+-----+-----+-----+-----+-------+ +-----+
+-------+-----+-----+-----+-----+-----+-----+-----+-----+-----+-----+-----+-----+-----+ +-----+
|  Tab  |  Q  |  W  |  E  |  R  |  T  |  Y  |  U  |  I  |  O  |  P  |  [  |  ]  |  \  | | Del |
+-------+-----+-----+-----+-----+-----+-----+-----+-----+-----+-----+-----+-----+-----+ +-----+
+---------+-----+-----+-----+-----+-----+-----+-----+-----+-----+-----+-----+---------+
|  LCtrl  |  A  |  S  |  D  |  F  |  G  |  H  |  J  |  K  |  L  |  ;  |  '  |  Enter  |
+---------+-----+-----+-----+-----+-----+-----+-----+-----+-----+-----+-----+---------+
+-----------+-----+-----+-----+-----+-----+-----+-----+-----+-----+-----+-----------+   +-----+
|  LS \'('  |  Z  |  X  |  C  |  V  |  B  |  N  |  M  |  ,  |  .  |  /  |  RS \')'  |   | Up  |
+-----------+-----+-----+-----+-----+-----+-----+-----+-----+-----+-----+-----------+   +-----+
+-------+-------+-------+-----------------------------+-------+-------+-------+   +-----+-----+-----+
| LCtrl | LMeta | LAlt  |            SpaceFn          | RA\LS | RMeta | RCtrl |   |Left |Down |Right|
+-------+-------+-------+-----------------------------+-------+-------+-------+   +-----+-----+-----+
```

## SpaceFn Layer

Hold `Space` for this layer. Release it to return to base.

```text
+-----+-----+-----+-----+-----+-----+-----+-----+-----+-----+-----+-----+-----+-------+ +-----+
|  ▽  | F1  | F2  | F3  | F4  | F5  | F6  | F7  | F8  | F9  | F10 | F11 | F12 |   ▽   | |  ▽  |
+-----+-----+-----+-----+-----+-----+-----+-----+-----+-----+-----+-----+-----+-------+ +-----+
+-------+-----+-----+-----+-----+-----+-----+-----+-----+-----+-----+-----+-----+-----+ +-----+
|   ▽   | Esc |  [  | Ret |  ]  | Tab | Ins |PgUp |  ↑  |PgDn |PrtSc|Prev |Next |  ▽  | |  ▽  |
+-------+-----+-----+-----+-----+-----+-----+-----+-----+-----+-----+-----+-----+-----+ +-----+
+---------+-----+-----+-----+-----+-----+-----+-----+-----+-----+-----+-----+---------+
|    ▽    | Alt | Spc | Del |Bspc |SelLn|Home |  ←  |  ↓  |  →  | End |  ▽  |    ▽    |
+---------+-----+-----+-----+-----+-----+-----+-----+-----+-----+-----+-----+---------+
+-----------+-----+-----+-----+-----+-----+-----+-----+-----+-----+-----+-----------+   +-----+
|     ▽     |RClk |LClk |Copy |Paste|Break|  =  |  -  | C←  | C→  |Menu |     ▽     |   | M↑  |
+-----------+-----+-----+-----+-----+-----+-----+-----+-----+-----+-----+-----------+   +-----+
+-------+-------+-------+-----------------------------+-------+-------+-------+   +-----+-----+-----+
|   ▽   |   ▽   |   ▽   |               ▽             |   ▽   |   ▽   | Caps  |   | M←  | M↓  | M→  |
+-------+-------+-------+-----------------------------+-------+-------+-------+   +-----+-----+-----+
```

## SpaceFn Key Reference

| Group                 | Physical keys         | `SpaceFn` action                                 |
| --------------------- | --------------------- | ------------------------------------------------ |
| Function keys         | `1`..`=`              | `F1`..`F12`                                      |
| Basic control         | `Q` / `E` / `T`       | Quit(Escape) / Enter / Tab                       |
| Brackets              | `W` / `R`             | `[` / `]`                                        |
| Insert and screenshot | `Y` / `P`             | Insert / PrintScreen: `Win+Shift+S`              |
| Arrow cluster         | `I` / `K` / `J` / `L` | Up / Down / Left / Right                         |
| Page movement         | `U` / `O`             | Page Up / Page Down                              |
| Line edges            | `H` / `;`             | Home / End                                       |
| App switching         | `[` / `]`             | Previous / next app: `Alt+Shift+Esc` / `Alt+Esc` |
| Left-hand editing     | `D` / `F` / `G`       | Delete / Backspace / Select current line         |
| Clipboard             | `C` / `V`             | Copy / paste via `Ctrl+Insert` / `Shift+Insert`  |
| Modifier and Space    | `A` / `S`             | Left Alt / Space                                 |
| Mouse clicks          | `Z` / `X`             | Mouse right / left click                         |
| Symbols and pause     | `B` / `N` / `M`       | Pause/Break / `=` / `-`                          |
| Word movement         | `,` / `.`             | Ctrl+Left / Ctrl+Right                           |
| Menu                  | `/`                   | Context Menu                                     |
| Mouse movement        | Arrow keys            | Accelerated mouse movement                       |
| CapsLock toggle       | `Right Ctrl`          | CapsLock                                         |

## Base Combos

These combos work on base only.
They are disabled inside `SpaceFn`, so fast edit chords stay deterministic.

| Keys    | Action          |
| ------- | --------------- |
| `Z + X` | Undo: `Ctrl+Z`  |
| `X + C` | Cut: `Ctrl+X`   |
| `C + V` | Copy: `Ctrl+C`  |
| `V + B` | Paste: `Ctrl+V` |
| `M + ,` | Volume down     |
| `M + .` | Volume up       |
| `, + .` | Mute            |

## References

- Kanata project: https://github.com/jtroo/kanata
- Kanata configuration guide: https://github.com/jtroo/kanata/blob/main/docs/config.adoc
- Kanata key names source: https://github.com/jtroo/kanata/blob/main/parser/src/keys/mod.rs
