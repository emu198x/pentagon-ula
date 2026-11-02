# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

## [0.2.1] - 2026-11-02

### Fixed

- Run the Pentagon 128 at 3.5 MHz from a 14 MHz master clock, as the original
  did, through `emu198x-bus-sinclair-zx-spectrum` 0.1.1: a 71,680 T-state frame
  lasts 20.48 ms, the Pentagon's 48.83 Hz refresh (emu198x/emu198x#2231).
  0.2.0 ran it at 14.336 MHz, the ZX Spectrum Next's VGA 50Hz Pentagon mode.

## 0.2.0

### Fixed

- Preserve pending video fetches, the border output latch and pipeline phase
  through the shared ULA engine 0.2.0. The positional serialized layout changes;
  callers must version their enclosing saves and reject older payloads before
  decoding. Hardware stepping and rendering algorithms are unchanged.

## 0.1.0

### Added

- Implements the `Ula` trait from `emu198x-bus-sinclair-zx-spectrum` over the
  engine in `emu198x-sinclair-zx-spectrum-ula`, where both moved from the
  family's glue crate; the crate no longer depends on `common-sinclair-zx-spectrum`.
- First release under the `emu198x-pentagon-ula` name. Until now the crate was
  `pentagon-ula`, versioned with the Emu198x suite and unpublished; the entries below are from that name.

## [0.2.0](https://github.com/emu198x/emu198x/releases/tag/pentagon-ula-v0.2.0) - 2026-06-04

### Other

- *(release)* independent per-machine versioning, baseline 0.2.0
- Open Emu198x for public release
- Tree housekeeping: project relocation paths + Cargo.lock
- Add Pentagon, Scorpion ZS-256, and Timex SCLD variant ULAs
