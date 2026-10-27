# Changelog

All notable changes to this project are documented in this file. The format
follows [Keep a Changelog](https://keepachangelog.com/en/1.1.0/), and the
project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

## [1.0.1] - 2026-10-27

### Fixed

- The firmware builds from a standalone clone placed next to an lwIP-CE
  checkout, not only from lwIP-CE's `wifi_bridge` submodule.

## [1.0.0] - 2026-10-27

### Added

- Wi-Fi bridge firmware for ESP32-S3 and ESP32-P4 boards, split out of
  [lwIP-CE](https://github.com/cagscalclabs/lwip-ce).
- Bridge board hardware: KiCad project, fabrication files and enclosure.

[Unreleased]: https://github.com/alessiodam/lwIP-CE-WiFi-bridge/compare/v1.0.1...HEAD
[1.0.1]: https://github.com/alessiodam/lwIP-CE-WiFi-bridge/compare/v1.0.0...v1.0.1
[1.0.0]: https://github.com/alessiodam/lwIP-CE-WiFi-bridge/releases/tag/v1.0.0
