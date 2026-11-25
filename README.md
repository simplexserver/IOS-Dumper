# SimpleX Toolkit — iOS Runtime & Engine Toolkit

**SimpleX Toolkit v1.1.0** is an iOS runtime inspection toolkit with an Unreal Engine 4 dumper and an experimental Unity IL2CPP metadata extractor.

The floating toolkit interface is designed to appear in normal UIKit user apps. When the current app does not match a supported engine, the menu reports **NOT SUPPORTED FOR THIS APP**, lists supported engine families, and keeps Logs, Files, Mach-O inventory, and the community contact link available.

## Downloads

- [Latest iOS dylib](Latest/SimpleXDumper.dylib)
- [Latest rootless Theos package](Latest/SimpleXDumper.deb)
- [Archived v1.1.0 dylib](Archive/v1.1.0/SimpleXDumper.dylib)
- [Archived v1.1.0 rootless package](Archive/v1.1.0/SimpleXDumper.deb)
- [v1.1.0 changelog](Archive/v1.1.0/CHANGELOG.md)
- [Previous v1.0.0 archive](Archive/v1.0.0/)

## Engine support

| Engine | Status | Capability |
| --- | --- | --- |
| Unreal Engine 4 | Supported when runtime layout/profile is compatible | object/name discovery, reflection output, generated C++ SDK, .usmap mappings, IDA/Ghidra mappings, Dumpspace JSON |
| Unity IL2CPP | Experimental | global-metadata.dat validation, metadata string extraction, managed string literal extraction, raw metadata preservation |
| Unity Mono | Not supported | no Mono runtime dumper in this release |
| Other engines | Not supported | toolkit menu and general iOS inspection utilities remain available |

### Unreal Engine 4

The UE4 pipeline retains the existing UEAnalyzerKitty discovery, automatic layout/offset detection, and per-title profile/decryption hooks. It can generate GObjects and reflection dumps, a C++ SDK with a validation test suite, UE4 mappings, IDA/Ghidra mapping output, and Dumpspace JSON. Compatibility depends on the game build, engine layout, and profile support; not every UE4 fork is guaranteed to work.

### Unity IL2CPP — experimental

The new iOS Unity component locates global-metadata.dat in common app-bundle locations, validates the metadata magic/version/section ranges, preserves the raw file, and exports MetadataStrings.txt and StringLiterals.txt alongside MetadataHeader.txt and Summary.txt.

The current parser accepts metadata versions 16–35 with the expected stable header prefix and 8-byte string-literal records. Version 38+ is rejected because its header/index layout changed. This is **not yet a complete Unity dumper**: assembly/type/field/method reconstruction, generics, native method address mapping, registration discovery, and protected metadata decryption are not implemented.

## Other toolkit modules

- Loaded app Mach-O image inventory using dyld enumeration; the UE module picker no longer relies on selecting only the two largest frameworks.
- KittyMemory-backed read-only memory-region and pointer inspection, safe scanning, and Mach-O inspection.
- Runtime logs and an in-app Files browser with multi-select, ZIP compression, delete, and the native iOS share sheet.
- UE4 runtime discovery report for GNames, GObjects, GEngine, GWorld, and ProcessEvent offsets when found.

KittyMemory is used as a low-level inspection dependency; SimpleX Toolkit does not expose memory patch/write controls.

## Compatibility

- Platform: iOS only
- Architecture: arm64
- Deployment target: iOS 14.0
- Package: rootless Theos .deb plus matching dylib
- Existing package identifier: com.simplex.simplexdumper (preserved for upgrades)
- Binary filenames remain SimpleXDumper.dylib and SimpleXDumper.deb for compatibility

The distributed binaries are unsigned. A standalone dylib requires a compatible injection/loading setup; it does not self-inject on stock iOS. Android is out of scope.

## Contact and credits

The in-app menu subtitle contains a clickable community/contact link (no separate credits button):

https://discord.gg/Kr2pvPfEUR

Use this tooling only with apps, games, and devices that are owned or authorized for inspection.
