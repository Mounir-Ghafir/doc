# Rust Installation — Summary

## 1. Installing Rust

- `rustup` is the tool used to install Rust and manage its versions.
- On Linux or macOS, install Rust by running:

```
curl --proto '=https' --tlsv1.2 https://sh.rustup.rs -sSf | sh
```

\- Follow the installation instructions and restart your terminal or reload its configuration if necessary.

## 2. Essential Rust Tools

| Tool      | Purpose                                                            |
| --------- | ------------------------------------------------------------------ |
| `rustup`  | Installs and manages Rust versions.                                |
| `rustc`   | Compiles Rust source code.                                         |
| `cargo`   | Creates projects, manages dependencies, builds, and runs programs. |
| `rustfmt` | Formats Rust code automatically.                                   |

## 3. Verifying the Installation

Check that Rust and Cargo are installed:

```
rustc --version
cargo --version
rustup --version
```

If a command is not found, check your `PATH` environment variable:

```
echo $PATH
```

On Linux, Rust tools are usually located in:

```
$HOME/.cargo/bin
```

If necessary, add this directory to `PATH` in `~/.bashrc`:

```
export PATH="$HOME/.cargo/bin:$PATH"
source ~/.bashrc
```

## 4. Installing Build Tools

Rust may require a linker to produce executable programs. On Linux Mint, install the essential build tools with:

```
sudo apt update
sudo apt install build-essential
```

This package includes GCC and other tools needed to compile and link programs.

## 5. Updating and Uninstalling Rust

Update Rust:

```
rustup update
```

Uninstall Rust:

```
rustup self uninstall
```

## 6. Offline Documentation

Rust includes local documentation that you can access without an internet connection:

```
rustup doc
```

Use this documentation to learn about standard library types, functions, and methods.

## 7. Working Offline with Cargo

Some Rust projects require external libraries called dependencies or crates.

To prepare dependencies for offline use:

```
cargo new get-dependencies
cd get-dependencies
cargo add rand@0.10.1 trpl@0.2.0
cargo fetch
```

- `cargo new` creates a new project.
- `cd` enters the project directory.
- `cargo add` adds dependencies to `Cargo.toml`.
- `cargo fetch` downloads the required dependencies for local use.
- `--offline` tells Cargo to use locally available dependencies without accessing the network.

Example:

```
cargo build --offline
```

Important: Offline commands may fail if a required dependency has not been downloaded or cached.

## 8. Terminal Command Notation

In the Rust book, `$` indicates a terminal prompt. You should not type the `$` character when executing a command.

For example, if the book shows:

```
$ cargo run
```

Type only:

```
cargo run
```

## Key Takeaway

To start developing with Rust, install `rustup`, verify that `rustc` and `cargo` work, install build tools if necessary, and learn to manage dependencies with Cargo. You can also use the local documentation and download dependencies in advance to work offline.