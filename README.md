# SimpleXDumper

**SimpleXDumper 1.0.0** is an iOS runtime dumper and SDK generator for Unreal Engine 4 (UE4) game builds.

Version 1.0.0 currently targets UE4. It is intended to help developers and authorized researchers inspect UE4 runtime metadata and generate structured SDK and mapping outputs from a compatible running game.

## Downloads

- [Latest iOS dylib](Latest/SimpleXDumper.dylib)
- [Latest rootless Theos package](Latest/SimpleXDumper.deb)
- [Version 1.0.0 changelog](Versions/v1.0.0/CHANGELOG.md)
- [Version 1.0.0 checksums](Versions/v1.0.0/SHA256SUMS.txt)

## UE4 capabilities

Depending on the target game's runtime layout and profile compatibility, SimpleXDumper can:

- Locate and analyze UE4 runtime structures, including the global object and name collections.
- Detect engine offsets and object/name container layouts at runtime.
- Generate object dumps and reflection metadata.
- Generate a C++ SDK.
- Generate .usmap mappings, IDA .idmap mappings, and Dumpspace JSON.
- Apply title-specific profiles for custom offsets, pointer layouts, or encrypted UE4 fields.
- Produce a timestamped Dump_... archive and a SimpleXDumper.log log.

This is multi-title UE4 tooling, not a guarantee that every UE4 game works without adjustments. UE4 forks, engine versions, custom allocators, anti-tamper behavior, and game-specific encryption can require a compatible profile or additional research.

## Platform and package

| Item | v1.0.0 |
| --- | --- |
| Platform | iOS |
| Architecture | arm64 |
| Deployment target | iOS 14.0 |
| Package | Rootless Theos .deb |
| Runtime library | SimpleXDumper.dylib |
| Engine support | UE4 |

The .deb is a rootless jailbreak tweak package. The standalone dylib requires a compatible injection/loading setup; the dylib does not self-inject on stock iOS. The distributed binaries are unsigned.

## Future engine support

- **Unity — planned.** Unity support is not implemented in v1.0.0.
- Additional engine families and game-specific UE4 profiles may be evaluated for later versions.

## Discord / credits

The in-app Discord / Credits action copies the invite and attempts to open the community server:

https://discord.gg/Kr2pvPfEUR

## Release structure

- Latest/ contains the current dylib, Debian package, and checksums.
- Versions/v1.0.0/ preserves the versioned binaries, checksums, and changelog.

This public repository is a binary-release channel. Project source and build configuration are maintained separately.

Use the tool only with games, apps, and devices that you own or are authorized to inspect.
