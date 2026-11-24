# SimpleXDumper 1.0.0

## Initial branded release

- Establishes the SimpleXDumper product identity and version 1.0.0.
- Adds the in-app Discord / Credits action. It copies the invite and attempts to open Discord: https://discord.gg/Kr2pvPfEUR.
- Labels the dump action iOS UE4 Dumper.
- Uses SimpleXDumper for the runtime/log identifier and SimpleXDumper.log for the log file.
- Uses Dump_ as the prefix for generated dump directories and ZIP archives.
- Renames the iOS tweak binary and package identity to SimpleXDumper.
- Keeps the iOS output set focused on UE4 object/reflection data, generated C++ SDK, mappings, IDA mappings, and Dumpspace output.

## Compatibility

- iOS arm64.
- iOS deployment target: 14.0.
- Rootless Theos package and matching dylib.
- UE4 only in this version. Game compatibility depends on supported layouts and any game-specific profile or decryption requirements.

## Planned

- Unity runtime support is planned for a future release. It is not part of v1.0.0.
