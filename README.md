# repocard

![repocard](https://repocard.dannyben.com/svg/repocard.svg)

Generate a simple SVG repo card that summarizes repository metadata from a tiny
config file. Supports any number of cards and arbitrary Label=Value pairs.

## Install

Download the executable [`repocard`][executable] bash script to any directory
that is already in your PATH. 

```shell
# This downloads the latest release version
wget https://get.dannyb.co/repocard
sudo install repocard /usr/local/bin
```

## Usage

Create a config file (default is `./.repocard.conf`) and run:

```shell
repocard > repocard.svg
```

Or with an explicit config path:

```shell
repocard path/to.conf > repocard.svg
```

## Minimal config

Only items are required. All other settings have defaults.

```ini
item=Development Status|green|Actively Developed
item=Code Base Status|blue|Beta
```

## Full config

<details>
<summary>Show full config example</summary>

```ini
caption=Repo Card
cols=3
width=220
height=65
gap=12
padding=16
bg=f7f7f5
bg_dark=161b22
title=1f2328
title_dark=f0f6fc
label=5a6572
label_dark=8b949e
border=e6e6e2
border_dark=30363d
card=ffffff
card_dark=0d1117

green=22C55E
green_dark=22C55E
yellow=EAB308
yellow_dark=EAB308
orange=F97316
orange_dark=F97316
red=EF4444
red_dark=EF4444
blue=3B82F6
blue_dark=3B82F6
neutral=8F8F8F
neutral_dark=A3A3A3
strong=222222
strong_dark=dddddd

item=Development Status|green|Actively Developed
item=Code Base Status|blue|Beta
item=Maintenance Status|red|Abandoned
```

</details>

## Config notes

- One `item=` per line, format is `Label|color|Value`
- Theme-aware defaults are built in via SVG CSS (`prefers-color-scheme`)
- `padding` defaults to `16`
- `bg` defaults to `f7f7f5` in light theme and `161b22` in dark theme
- Supported colors: `green, yellow, orange, red, blue, strong, neutral`
- Empty `caption` hides the title row
- `bg`, `card`, and `border` accept hex values or `transparent`/`none`
- Any color key can define a dark override with `_dark` (example: `title_dark`, `green_dark`)
- `title` controls the caption text color; `label` controls the label text color


[executable]: https://github.com/DannyBen/repocard/blob/master/repocard
