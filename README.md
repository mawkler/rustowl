# RustOwl

Visualize Ownership and Lifetimes on Rust

## Quick Start

Quick start guide using Docker.

### Prerequisite

- Docker installed, `docker` command is available, and Docker Engine started
- Visual Studio Code (VSCode) installed

We tested this guide on macOS Sonoma 14.6.1 on arm64 architecture with docker 26.0.0 and VSCode 1.95.1.

### Download VSCode extension

Download VSCode extension file ( `.vsix` ) from [this link](https://github.com/cordx56/rustowl/releases/latest/download/rustowl-vscode-0.0.1.vsix).

### Install VSCode extension

Press `Cmd+Shift+P` on macOS or `Ctrl+Shift+P` on other systems to open the command palette in VSCode.
Type `install vsix` in the command palette, and `Extensions: Install from VSIX...` will appear.
Click it and select the downloaded `.vsix` file.
The extension will then be installed.

## Build manually

Here, we describe manual install instructions from source code.

### HTTP server

#### Prerequisite

- `rustup` installed
    - You can install `rustup` from [this link](https://rustup.rs/).
    - You need to set up the `PATH` environment variable. To do this, follow the instructions provided by the `rustup` installer. For example, in bash, run `export PATH=$HOME/.cargo/bin:$PATH`.

HTTP server has been tested on macOS Sonoma 14.6.1 on arm64 architecture with `rustup` 1.27.1.
We have not tested the installation of dependencies from other package repositories, such as Homebrew. You may need to uninstall any Rust-related packages installed through those repositories first.
Other dependencies are locked in the configuration files and will be installed automatically.

We have also tested this on Ubuntu 24.04.1 on amd64 architecture with rustup 1.27.1.

Additional dependencies may be required.
We have confirmed that running `apt install -y build-essential` is necessary on a freshly installed Ubuntu for linking.

#### Build & Run

```bash
cd rustowl-server
cargo run
```


### VSCode extension

#### Prerequisite

- VSCode installed
    - You can install VSCode from [this link](https://code.visualstudio.com/).
- Node.js installed
- `yarn` installed
    - After installing Node.js, You can install `yarn` by running `npm install -g yarn`.

VSCode extension has been tested on macOS Sonoma 14.6.1 on arm64 architecture with Visual Studio Code 1.95.1, nodejs v20.16.0, and `yarn` 1.22.22.
Other dependencies are locked in the configuration files and will be installed automatically.

#### Build & Run

First, install the dependencies.

```bash
cd rustowl-vscode
yarn install --frozen-locked
```

Then open `rustowl-vscode` directory in VSCode.

A notification to install the recommended VSCode extension will appear in the bottom right corner of VSCode.
Click the install button, wait for the installation to finish, and then restart VSCode.

Open `rustowl-vscode` directory again, and press the `F5` key in the VSCode window.
A new VSCode window with the extension enabled will appear.

Open `rustowl-vscode/sample.rs` in the new VSCode window.

When you make changes to Rust files, annotations indicating the movement of ownership and lifetimes will appear in the editor.
