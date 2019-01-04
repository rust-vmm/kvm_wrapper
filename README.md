# kvm_wrapper
Rust FFI bindings to KVM generated using
[bindgen](https://crates.io/crates/bindgen). It currently has support for the
following target architectures:
- x86
- x86_64
- arm

# Usage
First, add the following to your `Cargo.toml`:
```toml
kvm_wrapper = "0.1"
```
Next, add this to your crate root:
```rust
extern crate kvm_wrapper;
```
By default `kvm_wrapper` will export a wrapper over the latest available kernel
version (4.20), but you can select a different version by specifying it in your
toml:
```toml
kvm_wrapper = { version = "0.1.0", features = ["kvm_v4_20_0"]}
```
In the `kvm_wrapper` crate each feature maps to exactly one Linux version
as follows:
- `kvm_v4_14_0` contains the bindings for the Linux kernel version 4.14
- `kvm_v4_20_0` contains the bindings for the Linux kernel version 4.20
