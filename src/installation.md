# Installation

<!-- TOC -->

- [Official Binaries](#official-binaries)
  - [Stable Releases](#stable-releases)
  - [Unstable Builds](#unstable-builds)
- [From Source](#from-source)

<!-- /TOC -->

## Official Binaries

### Stable Releases

#### [cargo-binstall](https://crates.io/crates/cargo-binstall)

```bash
cargo binstall pace-rs
```

<!-- TODO! #### Windows

##### [Scoop](https://scoop.sh/)

```bash
scoop install pace
``` -->

You can download the latest stable release versions of pace from the
[pace release page](https://github.com/pace-rs/pace/releases/latest). These
builds are considered stable and releases are made regularly in a controlled
manner.

There's both pre-compiled binaries for different platforms as well as the source
code available for download. Just download and run the one matching your system.

## From Source

**Beware**: This installs the latest development version, which might be
unstable.

pace is written in Rust and you need a current Rust version.

In order to build pace from source, execute the following steps:

### Github

```bash
cargo install --git https://github.com/pace-rs/pace.git pace-rs
```

### crates.io

You can also directly install the latest crate from crates.io.

```bash
cargo install pace-rs
```
