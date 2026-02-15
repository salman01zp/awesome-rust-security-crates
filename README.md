# awesome-rust-security-crates


## 1. `cargo-geiger`
A tool that lists statistics related to the usage of unsafe Rust code in a Rust crate and all its dependencies.
https://github.com/geiger-rs/cargo-geiger

## 2. `cargo-audit`
Audit Cargo.lock for crates with security vulnerabilities
https://crates.io/crates/cargo-audit

## 3. `valgrind`
Detect memory leaks, debugging memory management issues, and profiling applications
https://valgrind.org/

### Install valgrind
sudo apt install valgrind

### Build with debugging symbols
cargo build --profile profiling

### Run with memory checking
valgrind --tool=memcheck \
  --leak-check=full \
  --show-leak-kinds=all \
  target/profiling/relay

### Install heaptrack
sudo apt install heaptrack

### Profile memory usage
heaptrack target/release/relay

### Analyze results
heaptrack_gui heaptrack.relay.123.gz