<p align="center">
  <img src="media/bflogo/bflogo.svg" alt="Boxflinger Logo" width="500">
</p>

<p align="center">
  <a href="https://codeberg.org/ideumi/boxflinger/releases"><img src="https://img.shields.io/gitea/v/release/ideumi/boxflinger?gitea_url=https%3A%2F%2Fcodeberg.org&label=release" alt="Latest release"/></a>
</p>

# boxflinger

A collection of simple terminal UI primitives and widgets for the [Chippy](https://codeberg.org/ideumi/chippy) programming language.

### [View Releases](https://codeberg.org/ideumi/boxflinger/releases)

## Features

- **Widgets**: Text input, number input, multi-line editor, menus, lists, radio buttons, checkboxes, sliders, message and confirm dialogs, keybinds bar
- **Drawing**: Boxes, frames, lines, progress bars, buttons
- **Text**: Clipping, padding, wrapping, alignment
- **Layout**: Proportional horizontal / vertical splitting, dialog centering
- **Graphics**: Image display via the [Kitty Graphics Protocol](https://sw.kovidgoyal.net/kitty/graphics-protocol/)

See the [depthfinder](https://codeberg.org/ideumi/depthfinder) file manager for an example on how boxflinger is used in action.

## Screenshots

<p align="left">
  <img src="media/screensh_test.png" alt="Main Demo" width="384">
  <img src="media/screensh_test_select.png" alt="Select Widget" width="384">
</p>

<p align="left">
  <img src="media/screensh_test_check.png" alt="Checkbox List" width="384">
  <img src="media/screensh_test_editor.png" alt="Text Editor" width="384">
</p>

## Requirements

- [Chippy](https://codeberg.org/ideumi/chippy) >= 1.0.21

## Using boxflinger

Download the latest `libboxflinger.chh` from the [releases](https://codeberg.org/ideumi/boxflinger/releases) page or [build](#building) it yourself.

Copy the `libboxflinger.chh` to a directory in your project where `chippy combine` can find it, e.g. `lib/`:

`combine.chp`:
```chippy
# Combine configuration file
...

# Search paths for dependencies

var Paths = [];
Paths = Paths + ["src"];
Paths = Paths + ["lib"]; # here

...
```

then load it in your program:

e.g. `main.chp`:
```chippy
load("libboxflinger.chh");

...
```

Combine will resolve any dependencies that boxflinger needs from the corelib automatically.

## Documentation

Use `chippy doc` to view full documentation:

```bash
chippy doc libboxflinger.chh                                          # List all symbols
chippy doc libboxflinger.chh "BFMenu(x, y, items, defaultIndex)"      # Show documentation for BFMenu
chippy doc libboxflinger.chh all                                      # Show documentation for all symbols
```

## Building

See the [Requirements](#requirements), additionally you will need to have `git` installed:

```bash
git clone https://codeberg.org/ideumi/boxflinger
cd boxflinger
mkdir out

chippy combine
```

## Demo

Try the interactive demo:

```bash
cd demo/bftest
mkdir out
chippy combine

./out/bftest
```

The [Kitty](https://sw.kovidgoyal.net/kitty/graphics-protocol/) terminal is recommended for the demo.

## License

boxflinger is licensed under the 2-Clause BSD License. See `LICENCE.txt`.
