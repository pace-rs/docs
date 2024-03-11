# Installation

<!-- TOC -->

- [Official Binaries](#official-binaries)
  - [Stable Releases](#stable-releases)
- [From Source](#from-source)

<!-- /TOC -->

## Official Binaries

### Stable Releases

#### [cargo-binstall](https://crates.io/crates/cargo-binstall)

```bash
cargo binstall pace-rs
```

#### Windows

##### [Scoop](https://scoop.sh/)

```bash
scoop bucket add pace https://github.com/pace-rs/pace/
scoop install pace
```

#### MacOS

##### [Homebrew](https://brew.sh/)

You can use our tap:

```bash
brew install pace-rs/homebrew-tap/pace-rs
```

#### From GitHub

You can download the latest stable release versions of pace from the
[pace release page](https://github.com/pace-rs/pace/releases/latest). These
builds are considered stable and releases are made regularly in a controlled
manner.

There's both pre-compiled binaries for different platforms as well as the source
code available for download.

### From source

**Beware**: This installs the latest development version, which might be
unstable.

```bash
cargo install --git https://github.com/pace-rs/pace.git pace-rs
```

### crates.io

```bash
cargo install pace-rs
```
