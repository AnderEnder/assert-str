# assert-str

[![build status](https://github.com/AnderEnder/assert-str/workflows/Build/badge.svg)](https://github.com/AnderEnder/assert-str/actions)
[![codecov](https://codecov.io/gh/AnderEnder/assert-str/branch/master/graph/badge.svg)](https://codecov.io/gh/AnderEnder/assert-str)
[![crates.io](https://img.shields.io/crates/v/assert-str.svg)](https://crates.io/crates/assert-str)

Macros for asserting multiline strings

These are a set of macros to assert strings which could be generated on different operation systems, containing different new line character, or could contain different identation level. Such macros allows to compare prettified json or xml with compressed version.

## Usage

Add this to your Cargo.toml:

```toml
[dependencies]
assert-str = "0.1"
```

And import macros

```rust
use assert_str::{assert_str_eq, assert_str_ne};
use assert_str::{assert_str_trim_eq, assert_str_trim_ne};
use assert_str::{assert_str_trim_all_eq, assert_str_trim_all_ne};
```
