# assert-str

[![build status](https://github.com/AnderEnder/assert-str/workflows/Build/badge.svg)](https://github.com/AnderEnder/assert-str/actions)
[![codecov](https://codecov.io/gh/AnderEnder/assert-str/branch/master/graph/badge.svg)](https://codecov.io/gh/AnderEnder/assert-str)
[![crates.io](https://img.shields.io/crates/v/assert-str.svg)](https://crates.io/crates/assert-str)

Macros for asserting multiline strings

This is a set of macros to assert strings which could be generated on different operation systems, containing different new line character, or could contain different identation level. Such macros allows to compare prettified json or xml with compressed version.

## Usage

Add the dependency to your Cargo.toml:

```toml
[dependencies]
assert-str = "0.1"
```

or

```toml
[dev-dependencies]
assert-str = "0.1"
```

Import macros in the code

```rust
use assert_str::{assert_str_eq, assert_str_ne};
use assert_str::{assert_str_trim_eq, assert_str_trim_ne};
use assert_str::{assert_str_trim_all_eq, assert_str_trim_all_ne};
```

And use

```
assert_str_trim_eq!("<html>\t \n\t<head> \n\t</head></html>",
    "<html>\r\n<head>\r\n</head></html>", "Responces should be equal");
assert_str_trim_all_eq!("<html>\t \n\t<head> \n\t</head></html>",
    "<html><head></head></html>", "Responces should be equal");
```
