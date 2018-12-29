<img alt="Logo for the Rust programming language" src="https://www.rust-lang.org/logos/rust-logo-256x256-blk.png" style="float:left" height="128" width="128">

# Ansible Role: Rust

[![Build Status](https://img.shields.io/travis/fubarhouse/ansible-role-rust/master.svg?style=for-the-badge)](https://travis-ci.org/fubarhouse/ansible-role-rust)
[![stability-stable](https://img.shields.io/badge/stability-stable-green.svg?style=for-the-badge)](https://github.com/orangemug/stability-badges)
[![Ansible Rust](https://img.shields.io/ansible/role/22497.svg?style=for-the-badge)](https://galaxy.ansible.com/fubarhouse/rust)
[![MIT licensed](https://img.shields.io/badge/license-MIT-blue.svg?style=for-the-badge)](https://raw.githubusercontent.com/fubarhouse/ansible-role-rust/master/LICENSE)

* Install Rust from source (when configured)
* Install Rust from recommended installer
* Install cargo packages
* Support 20 linux platforms, as done by the Go and Node roles.

## Requirements

  * curl
  * gcc

## Role Variables

The version of rust is dependent on a source installation.
````
rust_version: 1.31.0
````

By default, the role will not install from source.
````
build_rust_from_source: false
````

After any initial installation, you can make sure the script updates Rust using:
````
rust_update: false
````

To ensure a clean installation on each playbook run, you can use:
````
rust_install_clean: false
````

To ensure the role installs to your shell profiles, you can specify them:
````
shell_profiles:
- .bash_profile
````

And, to install any cargo you can use the `cargo_items` array.
The `binary` property is optional, and when specified the binary installation will be verified.
````
cargo_items:
  - name: ripgrep
    binary: rg
````

## Installation

* Install using `ansible-galaxy install fubarhouse.rust`
* Add this role to your playbook.
* Modify above variables as desired.

## License

MIT / BSD

## Author Information

This role was created in 2017 by [Karl Hepworth](https://twitter.com/fubarhouse).