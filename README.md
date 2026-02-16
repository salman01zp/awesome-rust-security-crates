# awesome-rust-security-crates


## 1. `cargo-geiger`
A tool that lists statistics related to the usage of unsafe Rust code in a Rust crate and all its dependencies.
https://github.com/geiger-rs/cargo-geiger

## 2. `cargo-audit`
Audit Cargo.lock for crates with security vulnerabilities
https://crates.io/crates/cargo-audit

## Memory Profiling
Detect memory leaks, debugging memory management issues, and profiling applications
https://valgrind.org/

### Install valgrind
```
sudo apt install valgrind
```

### Build with debugging symbols
```
cargo build --profile profiling
```

### Run with memory checking
```valgrind --tool=memcheck \
  --leak-check=full \
  --show-leak-kinds=all \
  target/profiling/relay
```

### Install heaptrack
```
sudo apt install heaptrack
```

### Profile memory usage
```
heaptrack target/release/relay
```

### Analyze results
```
heaptrack_gui heaptrack.relay.123.gz
```

## 4. CPU profiling
### Using perf
```
# Install perf
sudo apt install linux-perf

# Record performance data
perf record -g target/release/relay

# Generate flame graph
perf script | ./flamegraph.pl > relay-flamegraph.svg
```
### Using flamegrapgh
```
# Install flamegraph
cargo install flamegraph

# Generate flame graph
cargo flamegraph --bin relay
```

## 5. Loom
Loom is a testing tool for concurrent Rust code. It runs a test many times, permuting the possible concurrent executions
https://github.com/tokio-rs/loom


## 6. Tower
Tower is a library of modular and reusable components for building robust networking clients and servers.
Generic components, like timeout, rate limiting, and load balancing, can be modeled as Services that wrap some inner service and apply additional behavior before or after the inner service is called. This allows implementing these components in a protocol-agnostic, composable way. Typically, such services are referred to as middleware.
https://github.com/tower-rs/tower/tree/master/guides