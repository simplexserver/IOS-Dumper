# SimpleXDumper v1.0.0

## Initial branded release

- Introduces the SimpleXDumper product identity and runtime version 1.0.0.
- Renames the iOS tweak, rootless package, and runtime library to SimpleXDumper.
- Uses **SimpleXDumper** as the in-app product title and **iOS UE4 Dumper** as the dump action/alert label.
- Adds an in-app **Discord / Credits** button that copies the invite and attempts to open the community server: https://discord.gg/Kr2pvPfEUR.
- Uses `SimpleXDumper.log` for the generated log file.
- Uses `Dump_` as the prefix for generated dump directories and archives.
- Retains UE4 reflection/object inspection and output generation for C++ SDK, UE4 mappings, IDA mappings, and Dumpspace JSON.

## Compatibility

- iOS arm64.
- iOS 14.0 deployment target.
- Rootless Theos package and matching dylib.
- UE4 only in this version. Compatibility across titles depends on engine layout and any required title-specific profile or decryption support.
- Distributed binaries are unsigned.

## Planned

- Unity runtime support is planned for a later version. It is not included in v1.0.0.
- Additional UE4 profiles and other engine families may be evaluated for future releases.
