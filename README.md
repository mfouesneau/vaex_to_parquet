# Exploring Rust with a template project

VSCode Rust project template for use with cargo

- prelinimary project structure
  - `src/*.rs`, source code of the project
  - `Cargo.toml`, project definition and configuration
- Usual files
  - `LICENSE`, licensing and copyright notice
  - `CODE_OF_CONDUCT`, code of conduct expected by the project
  - `CITATION.cff`, copyright notice
  - `CONTRIBUTING.md`, contributing notice
- Git repository
  - `.gitignore`, set to ignore build directory (`target`) and lock files
  - `.github/workflows`, set to contains minimal CI workflow (check, unit tests, rustfmt, clippy)
  - `.github/ISSUE_TEMPLATE`, set to contain minimal bug report template
- vscode et al.
  - `.vscode/settings.json`, set to contain minimal rust settings
  - `.vscode/tasks.json`, set to contain minimal test task
  - `.vscode/launch.json`, set to contain minimal test launch task

## Containers

### Devcontainer / GitHub Codespace

[![Open in GitHub Codespaces](https://github.com/codespaces/badge.svg)](https://codespaces.new/mfouesneau/gitpod-rust-project?quickstart=1)

A [`devcontainer`](https://containers.dev/) (short for Development Container) allows you to use a container as a full-featured development environment.
It provides a consistent and reproducible environment for developing code, regardless of the underlying operating system or development machine.

Devcontainers are typically defined using a `.devcontainer/devcontainer.json` file, which contains metadata and settings required to configure the development container.
This file defines the tooling and runtime stack needed for your project, such as the programming language, dependencies, and extensions.

This repository is setup to run the minimal [Rust image](https://mcr.microsoft.com/en-us/product/devcontainers/rust/about) with some vscode extensions for rust code developments.

### Gitpod

[![Open in Gitpod](https://gitpod.io/button/open-in-gitpod.svg)](https://gitpod.io/#https://github.com/mfouesneau/gitpod-rust-project)

Gitpod is a friendly online IDE very similar to VSCode ([Gitpod.io](https://gitpod.io/)
In particular, it provides an entire container-based platform (not saying Docker) and provides varied CDE features such as pair-coding while still compiling and running codes. It's also very convenient to write/edit and run some codes rapidly.
You can pick your working environement (VSCode, JetBrain, Terminal, etc.)

Sadly the support for devcontainers is under development and we need to define `gitpod.yml` configuration instead.

This repository sets a similar basic workspace to the devcontainer to start a rust project and work with Gitpod.

### Notebook (optional)

The [EvCxR Jupyter Kernel](https://github.com/evcxr/evcxr) (pronounced "Evic-ser") allows us to execute Rust code in a Jupyter Notebook.

You can install it by running the following command in a terminal:

```bash
cargo install evcxr_jupyter && evcxr_jupyter --install
```

ℹ️ you need jupyter installed on your system even if you use vscode. In the latter, you also need the `ms-toolsai.jupyter` extension to use jupyter kernels.

By default the containers do not install jupyter or the kernel to remain rapidly usable.
For the containers, you can install it by running the following command in a terminal:

```bash
sudo apt update && sudo apt install -y jupyter
cargo install evcxr_jupyter && evcxr_jupyter --install
```

An example of notebook is provided in the `notebooks` folder.
