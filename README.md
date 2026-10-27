# lwIP-CE Wi-Fi bridge

ESP32 firmware and hardware that give a TI-84 Plus CE running
[lwIP-CE](https://github.com/cagscalclabs/lwip-ce) Wi-Fi over the calculator's
USB port. See the lwIP-CE [Wi-Fi guide](https://github.com/cagscalclabs/lwip-ce/blob/master/docs/using-wifi.rst)
for setup and flashing.

## Building

The firmware shares `src/wireless/wifi_proto.h` with lwIP-CE. Clone this
repo next to an lwIP-CE checkout:

```sh
git clone https://github.com/cagscalclabs/lwip-ce.git
git clone https://github.com/alessiodam/lwIP-CE-WiFi-bridge.git lwip-ce-wifi-bridge
idf.py -C lwip-ce-wifi-bridge set-target esp32s3 build
```

It also builds as lwIP-CE's `wifi_bridge` submodule
(`idf.py -C lwip-ce/wifi_bridge build`).

ESP-IDF and lwIP-CE versions used by CI are pinned in `.github/ci-versions.env`.

## Versioning

The project follows [Semantic Versioning 2.0.0](https://semver.org/spec/v2.0.0.html).
`version.txt` holds the version. ESP-IDF builds it into the firmware, which
reports it to the calculator and the flasher.

- MAJOR: a change that breaks lwIP-CE or saved Wi-Fi profiles.
- MINOR: a new feature that older lwIP-CE builds still work with.
- PATCH: a fix that changes no behavior lwIP-CE relies on.

Every pull request that changes the firmware or hardware raises
`version.txt` and adds a matching section to `CHANGELOG.md`. Merging a new
version into `main` tags `v<version>` and publishes a GitHub release with the
firmware and fabrication files. A version with a pre-release part, such as
`1.1.0-rc.1`, publishes a pre-release.

## License

Copyright Alessio D'Ambrosio. The firmware, hardware design and enclosure are
licensed under [CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/)
(see `LICENSE`). You may share and adapt them for noncommercial purposes,
with attribution, and must release your changes under the same license.
Commercial use needs written permission.
