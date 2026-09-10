# niri-column-indicator

A compact indicator for columns in niri's scrolling layout. It marks the
focused column and updates from niri's direct IPC event stream.

**Requirements:** `niri` and a Rust toolchain with Cargo.

## Build

Clone the repository and build:

```sh
git clone https://github.com/viacoffee/niri-column-indicator.git
cd niri-column-indicator
cargo build --release
```

The binary is written to `target/release/niri-column-indicator`.

## Install

From the repository root, install the release binary with Cargo:

```sh
cargo install --path . --locked
```

Cargo installs it in its bin directory, usually `~/.cargo/bin`. Ensure that directory is on the `PATH` used by your bar.

To install it in `~/.local/bin` instead:

```sh
cargo install --path . --locked --root ~/.local
```

## Demo

The indicator in this demo appears on the right side of the bar.

https://github.com/user-attachments/assets/0aa50832-bfd5-48ae-9eae-a4c6566069be

## Usage

```sh
niri-column-indicator [--layout horizontal|vertical] [--inactive CHARACTER] [--active CHARACTER] [--hide-single] [--output=json|plain]
```

By default, output is JSON (used by Waybar custom modules). Use `--output=plain`
for line-oriented text output. Or [contribute](#integrations) a new output format!

| Option | Description |
| --- | --- |
| `--layout horizontal\|vertical` | Layout orientation. Default: `horizontal`. |
| `--inactive CHARACTER` | Indicator for an unfocused column. Default: `○`. |
| `--active CHARACTER` | Indicator for the focused column. Default: `●`. |
| `--hide-single` | Print no indicator when the workspace has zero or one column. |
| `--output=json\|plain` | Select output format. Default: `json`. |

## Integrations

- [Waybar](waybar/)

Integration examples for other bars are welcome. Add each example in its own
top-level directory and link it here. If an integration needs a new output
format, add it to [OutputFormat](src/main.rs).
