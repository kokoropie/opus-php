# opus-php

Opus bindings for PHP.

## Requirements

- PHP 8.1 or later.
- Linux, macOS, or Windows.
- [libopus 1.3.1 or later](https://opus-codec.org/downloads/) — required at runtime on Linux and macOS.

## Installation

### Pre-built binaries (recommended)

Download the extension for your platform and PHP version from the [Releases](../../releases) page.

| Platform | File |
|---|---|
| Linux | `libopusphp-linux-phpX.Y.so` |
| macOS | `libopusphp-macos-phpX.Y.dylib` |
| Windows | `libopusphp-windows-phpX.Y.dll` |

Then add the extension to your `php.ini`:

```ini
; Linux
extension=/path/to/libopusphp-linux-php8.2.so

; macOS
extension=/path/to/libopusphp-macos-php8.2.dylib

; Windows
extension=C:\path\to\libopusphp-windows-php8.2.dll
```

> **Linux/macOS:** `libopus` must be installed on the system at runtime.
> ```bash
> # Debian/Ubuntu
> sudo apt-get install libopus0
>
> # macOS
> brew install opus
> ```

### Build from source

**Prerequisites:**

- [Rust](https://rustup.rs/) (stable on Linux/macOS, nightly on Windows)
- Clang 5.0 or later
- libopus development headers
  ```bash
  # Debian/Ubuntu
  sudo apt-get install libopus-dev libclang-dev

  # macOS
  brew install opus

  # Windows — install via vcpkg
  vcpkg install opus:x64-windows
  ```

**Build:**

```bash
$ git clone https://github.com/kokoropie/opus-php.git
$ cd opus-php
$ cargo build --release
```

The compiled extension will be at:

- `target/release/libopus_php.so` (Linux)
- `target/release/libopus_php.dylib` (macOS)
- `target/release/opus_php.dll` (Windows)

## Releases

Pre-built binaries for Linux, macOS, and Windows are automatically built and published via GitHub Actions whenever a new version tag (`v*.*.*`) is pushed. Each release includes binaries for PHP 8.1 through 8.4.

## License

Licensed under the [MIT License](LICENSE).

Copyright (c) 2021 David Cole