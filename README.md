# espresso-gw - site-to-site gateway
A site-to-site VPN gateway for Linux, written in C++20: ESP with IP-TFS support, carried over UDP.

## Roadmap
- [ ] **Stage 0 — Infrastructure:** CMake build, GoogleTest, CI (GitHub Actions)
- [ ] **Stage 1 — Plaintext tunnel:** epoll event loop, TUN/UDP I/O, config, network-namespace test bench
- [ ] **Stage 2 — ESP with static keys:** tunnel mode, AEAD (OpenSSL), anti-replay, ESP-in-UDP (RFC 3948), interop with Linux xfrm
- [ ] **Stage 3 — Real deployment:** two remote hosts, systemd service, MTU tuning, iperf3 benchmarks
- [ ] **Stage 4 — Key exchange:** handshake (IKEv2 subset or Noise IK), rekeying
- [ ] **Stage 5 — IP-TFS (RFC 9347):** fixed-size frames, constant send rate
- [ ] **Stage 6 — Field testing:** deployment over a filtered network path, traffic measurements
- [ ] **Stage 7 — Pluggable transports:** obfuscation / protocol mimicry, based on Stage 6 results

## Build
From the repository root:

```bash
cmake -S . -B build        # configure
cmake --build build        # build
./build/<target_name>      # run
```

## License: [Apache 2.0](LICENSE)
