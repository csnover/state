# State

A Rust library for safe and effortless global and thread-local state management.

```rust
extern crate state;

static GLOBAL: state::Storage<u32> = state::Storage::new();

GLOBAL.set(42);
assert_eq!(*GLOBAL.get(), 42);
```

See the [documentation](https://sergio.bz/rustdocs/state) for more.

## Usage

Include `state` in your `Cargo.toml` `[dependencies]`:

```toml
[dependencies]
state = "0.3"
```

Thread-local state management is not enabled by default. You can enable it
via the `tls` feature:

```toml
[dependencies]
state = { version = "0.3", features = ["tls"] }
```

This crate requires Rust nightly due to the instability of the `const_fn`
feature. Ensure that it is enabled by adding the following to your top-level
crate attributes:

```rust
#![feature(const_fn)]
```

## License

State is licensed under either of the following, at your option:

 * Apache License, Version 2.0, ([LICENSE-APACHE](LICENSE-APACHE) or http://www.apache.org/licenses/LICENSE-2.0)
 * MIT License ([LICENSE-MIT](LICENSE-MIT) or http://opensource.org/licenses/MIT)
