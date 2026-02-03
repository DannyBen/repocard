# repocard

![repocard](repocard.svg)

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

```ini
layout=standard

caption=Repo Card
cols=3
width=220
height=65
gap=12
padding=16
bg=f7f7f5
title=1f2328
label=5a6572
border=e6e6e2
card=ffffff

red=cc3344
orange=d16c00
yellow=b78103
green=1a7f37
blue=0b62d6
black=1f2328
grey=6b7280

item=Development Status|green|Actively Developed
item=Code Base Status|blue|Beta
item=Maintenance Status|red|Abandoned
```

## Config notes

- One `item=` per line, format is `Label|color|Value`
- `layout` defaults to `standard`; `compact` changes defaults to `caption=""`, `bg=none`, `padding=0`
- Supported colors: `green, yellow, orange, red, blue, black, grey`
- Empty `caption` hides the title row
- `bg`, `card`, and `border` accept hex values or `transparent`/`none`
- `title` controls the caption text color; `label` controls the label text color


[executable]: https://github.com/DannyBen/repocard/blob/master/repocard
