# tokio-sunspec

A pure [Rust](https://www.rust-lang.org)
[SunSpec](https://en.wikipedia.org/wiki/SunSpec) library
based on [tokio](https://tokio.rs).

## Features

## Installation

```toml
[dependencies]
tokio-sunspec = "*"
```

## Examples

#### TCP Connect example for SMA Inverter

```rust
let socket_addr = "<ip-address>:502".parse().unwrap();
let device_id: u8 = 126;
let start_addr: u16 = 40000;

let mut client = tokio_sunspec::connect_tcp(socket_addr, device_id, start_addr).await?;

let res = client.read_point(model1::Mn).await?;
assert_eq!(res, "SMA");
```
