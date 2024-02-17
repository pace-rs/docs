<p align="center">
<img src="https://raw.githubusercontent.com/pace-rs/assets/main/logos/readme_header_docs.png" style="max-width:500px; width:100%; height: auto" />
</p>
<p align="center">
<b>user documentation</b>
</p>

<p align="center">
<a href="https://crates.io/crates/pace-rs"><img src="https://img.shields.io/crates/v/pace-rs.svg" /></a>
<a href="https://raw.githubusercontent.com/pace-rs/docs/main/LICENSE"><img src="https://img.shields.io/badge/license-MPL2.0-blue.svg" /></a>
<a href="https://crates.io/crates/pace-rs"><img src="https://img.shields.io/crates/d/pace-rs.svg" /></a>
<p>

An open source user documentation book for
[pace](https://github.com/pace-rs/pace) that you can read
[here](https://pace.cli.rs/docs).

## Installation

This book is built with [mdbook](https://rust-lang.github.io/mdBook/). You can
install it by running `cargo install mdbook`.

### Additional dependencies

- `cargo install mdbook-last-changed` for date changes in the footer

## Building with mdbook

If you want to build it locally you can run one of these two commands in the
root directory of the repository:

- `mdbook build`

  Builds static html pages as output and places them in the `/book` directory by
  default.

- `mdbook serve`

  Serves the book at `http://localhost:3000` (port is changeable, take a look at
  the terminal output to be sure) and reloads the browser when a change occurs.

## License

The content of this repository is licensed under **MPL-2.0**; see
[LICENSE](./LICENSE).
