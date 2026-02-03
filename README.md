# repo-status

Generate a simple, dashboard-like SVG for repo status badges from a tiny config file. Supports any number of cards and any Label=Value pairs.

![repo-status](/repo-status.svg)

## Install

Download the executable to your path.

## Usage

Create a config file (default is `./.repo-status.conf`) and run:

```
./repo-status > repo-status.svg
```

Or with an explicit config path:

```
./repo-status path/to/.repo-status.conf > repo-status.svg
```

## Minimal config

Only items are required. All other settings have defaults.

```ini
item=Development Status|green|Actively Developed
item=Code Base Status|blue|Beta
```

## Full config

```ini
title=Repo Status
cols=3
width=220
height=65
gap=12
padding=16
bg=f7f7f5
text=1f2328
muted=5a6572
border=e6e6e2
card=ffffff

green=1a7f37
yellow=b78103
orange=d16c00
red=cc3344
blue=0b62d6
black=1f2328
grey=6b7280

item=Development Status|green|Actively Developed
item=Code Base Status|blue|Beta
item=Maintenance Status|red|Abandoned
```

## Config notes

- One `item=` per line, format is `Label|color|Value`
- Supported colors: `green, yellow, orange, red, blue, black, grey`
- Empty `title` hides the title row
- `bg`, `card`, and `border` accept hex values or `transparent`/`none`
- `muted` controls the label text color (title uses `text`)
