# ttx.el

Inspect ttf/otf files as XML.

![screenshot](./screenshot.png)

## Installation

Add `ttx.el` to your load path and require it:

```elisp
(add-to-list 'load-path "/path/to/ttx-mode")
(require 'ttx)
```

## Requirements

[fonttools](https://github.com/fonttools/fonttools): The `ttx` command must be
installed and available in your system's `PATH`. If it is not in the `PATH`, the
location may be set within `ttx-command`.

```elisp
(setq ttx-command "/path/to/ttx")
```

## Usage

Open any `.ttf` or `.otf` file in Emacs. `ttx.el` will automatically trigger
`ttx-mode` and display the font's available tables. By default, the `head` and
`name` tables are loaded automatically. More tables can be loaded with
`ttx-load-table`.

### Keybindings

| Key       | Command            | Description                    |
|-----------|--------------------|--------------------------------|
| `C-c C-l` | `ttx-load-table`   | Load a table into the buffer   |
| `C-c C-k` | `ttx-unload-table` | Remove a table from the buffer |

To refresh the buffer (unload all tables): `M-x revert-buffer`

## Customization

### Default Tables

Configure which tables are loaded automatically when opening a font:

```elisp
(setq ttx-default-tables '("head" "name" "OS/2"))  ; load additional tables
(setq ttx-default-tables nil)                       ; start with skeleton only
```


## License


[GPL-3.0](LICENSE)
