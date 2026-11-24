# iOS Dumper

**SimpleXDumper v1.0.0** is an iOS runtime dumper and SDK generator for compatible Unreal Engine 4 (UE4) game builds.

The current release targets UE4 and is designed to work across multiple UE4-based game titles when their runtime layout and profile are compatible. It is developer/research tooling for inspecting a running UE4 process and generating structured metadata and SDK outputs; it does not promise universal compatibility with every UE4 fork or game build.

## Downloads

- [Latest iOS dylib](Latest/SimpleXDumper.dylib)
- [Latest rootless Theos package](Latest/SimpleXDumper.deb)
- [Archived v1.0.0 dylib](Archive/v1.0.0/SimpleXDumper.dylib)
- [Archived v1.0.0 rootless package](Archive/v1.0.0/SimpleXDumper.deb)
- [v1.0.0 changelog](Archive/v1.0.0/CHANGELOG.md)

## UE4 capabilities

Depending on the target game's engine version, memory layout, and profile compatibility, SimpleXDumper can:

- Locate and inspect UE4 runtime structures, including global object and name collections.
- Detect engine offsets and object/name container layouts at runtime.
- Generate object dumps and reflection metadata.
- Generate a C++ SDK from discovered runtime metadata.
- Generate UE4 `.usmap` mappings, IDA `.idmap` mappings, and Dumpspace JSON.
- Apply title-specific profiles for custom offsets, pointer layouts, or encrypted UE4 fields.
- Produce timestamped `Dump_...` output and a `SimpleXDumper.log` log.

It is intended as multi-title UE4 tooling. UE4 forks, engine revisions, custom allocators, encrypted fields, and anti-tamper behavior can require a compatible profile or additional work. A title should be treated as supported only after its runtime layout has been validated.

## Platform and package

| Item | v1.0.0 |
| --- | --- |
| Platform | iOS |
| Architecture | arm64 |
| Deployment target | iOS 14.0 |
| Package | Rootless Theos `.deb` |
| Runtime library | `SimpleXDumper.dylib` |
| Engine support | UE4 only |

The `.deb` is a rootless jailbreak tweak package. The standalone dylib requires a compatible injection/loading setup; it does not self-inject on stock iOS. The distributed binaries are unsigned.

## Future engine support

- **Unity — planned.** Unity runtime support is not implemented in v1.0.0.
- Additional engine families and game-specific UE4 profiles may be evaluated for future releases.

## Discord / credits

The in-app **Discord / Credits** button copies the invite and attempts to open the community server:

https://discord.gg/Kr2pvPfEUR

## Release structure

- `Latest/` contains only the current `.dylib` and `.deb`.
- `Archive/v1.0.0/` preserves the versioned `.dylib`, `.deb`, and changelog.

This is a public binary-release repository. The full project source, Theos build files, CI logs, and debug symbols remain in the private `simplexserver/Dumper-Build` repository. The workflow in `.github/workflows/build-private-source.yml` is an orchestration-only builder: it checks out the private source on an ephemeral runner and publishes only the release binaries and version changelog here. To run it, configure the `DUMPER_SOURCE_TOKEN` Actions secret with a fine-grained token limited to `simplexserver/Dumper-Build` and `Contents: Read` permission.

Use the tool only with games, apps, and devices that you own or are authorized to inspect.
