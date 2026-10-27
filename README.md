# Vim Configuration

A personal configuration for Vim and gVim, featuring editing options, colors, a status line, a tab line, and useful key mappings. No third-party plugins are required.

## Features

- Editing: line numbers, search highlighting, automatic indentation, four-space indentation, a status line, and a tab line.
- File formats: UTF-8 encoding and Unix (LF) line endings by default.
- Interface: a custom dark color scheme; gVim uses the system clipboard and starts with a configured window size, while terminal Vim disables the mouse.
- C++: additional syntax highlighting for commonly used standard library types.

> C++ files: When a `.h` or `.cpp` file is opened or selected, its buffer is set to Unix (LF) line endings and UTF-8 encoding. This overrides any manually selected line-ending format for these files.

## Installation

Copy the repository's `vimrc` to the user configuration path:

| Platform | User configuration path |
| --- | --- |
| Windows | `%USERPROFILE%\_vimrc` |
| FreeBSD | `~/.vimrc` |
| Linux | `~/.vimrc` |

You can also install it as a system-wide configuration:

| Platform | System configuration path |
| --- | --- |
| Windows | `C:\Program Files (x86)\Vim\.vimrc` |
| FreeBSD | `/usr/local/etc/vim/vimrc` |
| Linux | `/etc/vimrc` |

Restart Vim after copying the file. To load it immediately, run `:source <configuration-file-path>` in Vim.

## Key Mappings

| Key | Mode | Action |
| --- | --- | --- |
| `Alt` + arrow keys | Normal | Move the current line up or down; decrease or increase its indentation with the left or right arrow |
| `Alt` + arrow keys | Visual | Move the selected lines up or down; decrease or increase the selection's indentation with the left or right arrow |
| `F1` | Normal | Open Vim help in a new tab |
| `F5` | Normal | Reload the current file from disk and move to the end of the file |
| `F11` | Normal | Convert the current buffer to a hexadecimal display |
| `F12` | Normal | Open the options menu |
| `Tab` / `Shift` + `Tab` | Normal | Move backward / forward through the jump list |
| `n` / `N` | Normal | Go to the next / previous search match and center the cursor line |
| `p` | Visual | Paste while preserving the current selection |

- `F5` does not force-discard unsaved changes. Vim will prevent reloading a modified buffer.
- `F11` requires the `xxd` command to be available on your system. Run `:%!xxd -r` to convert the hexadecimal display back to its original content.

### F12 Options Menu

Press `F12` in Normal mode to open the menu. Press a number (`1`–`8`) to apply the corresponding action to the current buffer, or any other key to exit.

| Number | Menu item | Action |
| --- | --- | --- |
| `1` | `dos` / `unix` | Toggle the current buffer's line endings between DOS (CRLF) and Unix (LF). The menu shows the current format. |
| `2` | `utf-8` | Set the file encoding used when writing the current buffer to UTF-8. |
| `3` | `bomb` / `nobomb` | Toggle whether to write a byte order mark (BOM) at the start of the file. |
| `4` | `paste` / `nopaste` | Toggle Paste mode. |
| `5` | `list` / `nolist` | Toggle the display of whitespace characters. |
| `6` | `retab` | Remove trailing whitespace, trailing blank lines, and carriage returns at line ends, then reformat tabs using the current indentation settings. |
| `7` | `lazyredraw` / `nolazyredraw` | Toggle deferred screen redraws. |
| `8` | `unique` | Remove adjacent non-empty duplicate lines. Blank lines and duplicates separated by other lines are left unchanged. |
