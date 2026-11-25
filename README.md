# SimpleX Toolkit — iOS Runtime & Engine Toolkit

**SimpleX Toolkit v1.2.2** is an iOS runtime inspection and engine dumper with an Unreal Engine 4 pipeline and a live Unity IL2CPP runtime dumper.

## Files browser

Tap a folder to open it or a file to inspect it. Select mode adds checkboxes for batch sharing, renaming, and deleting. The plus button creates folders. Media and documents use iOS Quick Look; source and text files use a monospace viewer. Large text files load in 128 KiB pages instead of all at once into memory. Text files up to 512 KiB can be edited and atomically saved; bigger files stay paged and read-only. Directory scans run off the main thread.

## Logs console

Filters include All, Dump, Files, Unity, System, and Other, plus live search with the native iOS keyboard. Export shares whatever matches the active filter and search query. Tap outside the panel, hit close, or swipe up to dismiss it. History caps at 1,200 entries. Startup logs include timestamp, bundle ID, game/app version, iOS version, and hardware model.

## Downloads

- [Latest iOS dylib](Latest/SimpleXDumper.dylib)
- [Latest rootless package](Latest/SimpleXDumper.deb)
- [Archived v1.2.2 dylib](Archive/v1.2.2/SimpleXDumper.dylib)
- [Archived v1.2.2 package](Archive/v1.2.2/SimpleXDumper.deb)
- [v1.2.2 changelog](Archive/v1.2.2/CHANGELOG.md)
- [Previous v1.2.0 archive](Archive/v1.2.0/)
- [Previous v1.1.0 archive](Archive/v1.1.0/)
- [Previous v1.0.0 archive](Archive/v1.0.0/)

## Engine support

| Engine | Status | What it does |
| --- | --- | --- |
| Unreal Engine 4 | Supported when runtime layout/profile matches | object/name discovery, reflection dump, C++ SDK, .usmap, IDA/Ghidra mappings, Dumpspace JSON |
| Unity IL2CPP | Live runtime dumper added; needs per-game testing | assemblies/classes, fields/offsets, properties, methods/parameters, method RVAs, IDA Script.json, optional global-metadata export |
| Unity Mono | Not supported | no Mono runtime backend |
| Other engines | Not supported | opens in unsupported-app mode |

### Unreal Engine 4

The UE4 pipeline keeps layout/offset detection and per-game profile/decryption hooks. It outputs GObjects/reflection data, a C++ SDK with a validation suite, .usmap mappings, IDA/Ghidra mappings, and Dumpspace JSON. Support depends on the game build and runtime layout—not every UE4 fork works out of the box.

### Unity IL2CPP

The Unity dumper runs inside the live iOS app. It grabs IL2CPP exports from `UnityFramework` or `libil2cpp`, gets the domain, walks loaded assemblies, images, and classes, and writes:

- `Dump.cs` — combined runtime metadata declarations
- `Assembly/*.cs` — per-image/assembly declarations
- fields and field offsets, properties, methods, parameters, and method RVAs
- `Script.json` — native method RVA/name entries for IDA
- `Summary.txt` and `SimpleXUnity.log`
- optional raw metadata/string output when a supported `global-metadata.dat` layout is present

## Compatibility

- Platform: iOS only
- Architecture: arm64
- Deployment target: iOS 14.0+
- Package: rootless Theos `.deb` plus matching dylib
- Package ID: `com.simplex.simplexdumper` (kept for upgrades)
- Binary names: `SimpleXDumper.dylib` and `SimpleXDumper.deb`

Android isn't supported.

## Contact

Contact / credit link: https://discord.gg/Kr2pvPfEUR
