# SimpleX Toolkit — iOS Runtime & Engine Toolkit

**SimpleX Toolkit v1.2.0** is an iOS-only runtime inspection and engine dumper with an existing Unreal Engine 4 pipeline and a newly integrated live Unity IL2CPP runtime dumper.

The floating paw toggle appears in normal UIKit user apps. Unsupported apps display **NOT SUPPORTED FOR THIS APP** and the supported engine families. The menu retains the engine action(s), Logs, Files, and the clickable community/contact URL. The separate loaded-image inventory view is removed.

## Downloads

- [Latest iOS dylib](Latest/SimpleXDumper.dylib)
- [Latest rootless Theos package](Latest/SimpleXDumper.deb)
- [Archived v1.2.0 dylib](Archive/v1.2.0/SimpleXDumper.dylib)
- [Archived v1.2.0 rootless package](Archive/v1.2.0/SimpleXDumper.deb)
- [v1.2.0 changelog](Archive/v1.2.0/CHANGELOG.md)
- [Previous v1.1.0 archive](Archive/v1.1.0/)
- [Previous v1.0.0 archive](Archive/v1.0.0/)

## Engine support

| Engine | Status | Capability |
| --- | --- | --- |
| Unreal Engine 4 | Supported when runtime layout/profile is compatible | object/name discovery, reflection output, generated C++ SDK, .usmap, IDA/Ghidra mappings, Dumpspace JSON |
| Unity IL2CPP | Live runtime dumper integrated; game compatibility requires device validation | assemblies/classes, fields/offsets, properties, methods/parameters, method RVAs, IDA Script.json, optional global-metadata export |
| Unity Mono | Not supported | no Mono runtime backend |
| Other engines | Not supported | toolkit opens in unsupported-app mode |

### Unreal Engine 4

The existing UE4 pipeline retains UEAnalyzerKitty discovery, layout/offset detection, and per-game profile/decryption hooks. It generates GObjects/reflection data, a C++ SDK with a validation suite, .usmap mappings, IDA/Ghidra mappings, and Dumpspace JSON. Compatibility depends on the game build and runtime layout; not every UE4 fork is guaranteed to work.

### Unity IL2CPP

The Unity dumper runs inside the live iOS app. It resolves IL2CPP runtime exports from the loaded UnityFramework or libil2cpp image, obtains the IL2CPP domain, enumerates loaded assemblies/images/classes, and exports:

- `Dump.cs` — combined runtime metadata declarations
- `Assembly/*.cs` — per-image/assembly declarations
- fields and field offsets, properties, methods, parameters, and method RVAs
- `Script.json` — native method RVA/name records for the IDA workflow
- `Summary.txt` and `UnityDumper.log`
- optional raw metadata/string extraction when a supported global-metadata.dat layout is available

This is a live IL2CPP dumper, not only a string-table extractor. It still depends on an initialized runtime and accessible IL2CPP exports. Some builds strip or hide exports, use custom runtime layouts, encrypt/relocate metadata, or require game-specific work. It does not guarantee complete generic constraints, custom attributes, all registration layouts, or native code reconstruction. The optional raw metadata parser is separately limited to known stable header layouts. Unity Mono is not supported.

The runtime enumeration core is adapted under MIT; attribution and the original license are preserved in the private source repository.

## Compatibility

- Platform: iOS only
- Architecture: arm64
- Deployment target: iOS 14.0
- Package: rootless Theos .deb plus matching dylib
- Existing package identifier: `com.simplex.simplexdumper` (preserved for upgrades)
- Binary filenames remain `SimpleXDumper.dylib` and `SimpleXDumper.deb`

The distributed binaries are unsigned. A standalone dylib requires a compatible injection/loading setup; it does not self-inject on stock iOS. Android is out of scope.

## Contact

The menu subtitle contains a clickable community/contact link (no separate credits button):

https://discord.gg/Kr2pvPfEUR

Use this tooling only with apps, games, and devices that are owned or authorized for inspection.
