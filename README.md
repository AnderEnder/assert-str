# assert-str

[![build status](https://github.com/AnderEnder/assert-str/workflows/Build/badge.svg)](https://github.com/AnderEnder/assert-str/actions)
[![codecov](https://codecov.io/gh/AnderEnder/assert-str/branch/master/graph/badge.svg)](https://codecov.io/gh/AnderEnder/assert-str)
[![crates.io](https://img.shields.io/crates/v/assert-str.svg)](https://crates.io/crates/assert-str)

Macros for Asserting Multiline Strings

This is a set of macros designed to assert strings that may be generated on different operating systems, potentially containing different newline characters or varying levels of indentation. These macros allow you to compare prettified JSON or XML with their compressed versions.

## Usage

Add the dependency to your Cargo.toml:

```toml
[dependencies]
assert-str = "0.1"
```

Or

```toml
[dev-dependencies]
assert-str = "0.1"
```

Import the macros in your test module or main file:
```rust
use assert_str::{assert_str_eq, assert_str_ne};
use assert_str::{assert_str_trim_eq, assert_str_trim_ne};
use assert_str::{assert_str_trim_all_eq, assert_str_trim_all_ne};
```

Or if you want to import all macros:
```rust
use assert_str::*;
```

Use the macros:
```
#[test]
fn test_trimmed_string_assertions() {
    assert_str_trim_eq!(
        "<html>\t \n\t<head> \n\t</head></html>",
        "<html>\r\n<head>\r\n</head></html>",
        "Responses should be equal"
    );

    assert_str_trim_all_eq!(
        "<html>\t \n\t<head> \n\t</head></html>",
        "<html><head></head></html>",
        "Responses should be equal"
    );
}
```
* assert_str_trim_eq! ignores leading/trailing whitespace and normalizes line endings.
* assert_str_trim_all_eq! removes all whitespace (including between tags), useful for comparing minified and pretty-printed formats.
