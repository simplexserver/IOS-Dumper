# SimpleX Toolkit — iOS Runtime & Engine Toolkit

**SimpleX Toolkit v1.3.1** is an iOS-only runtime inspection toolkit with Unreal Engine 4 and Unity IL2CPP dumpers.

## Files and Game File Manager

- Tap a folder to open it and tap a file to inspect/edit it.
- Text/code files open directly in the editor. Save stays grey until content changes, then turns blue.
- Find highlights every case-insensitive match and shows a match count with previous/next navigation.
- Large text files remain paged to bound memory use.
- Recursive file search is case-insensitive and shows the containing folder for each result.
- Sort by name, size or modified date; filter by minimum size (1 MB / 10 MB).
- Long-press a file or folder for Open, Export / Share, Get Info, Rename, Move and Delete.
- Drag files/folders into folders to move them.
- The plus control creates either a folder or an empty file. Enter the complete file name and extension yourself.
- Game File Manager exposes Game Folder, Documents, Library, Caches, Temporary and App Bundle.
- App Bundle is browse-only; file operations and editing are disabled there.

## Logs console

Filters include All, Dump, Files, Unity, System, and Other, plus live search with the native iOS keyboard. Export shares the current filter/search result. Tap outside the panel, hit close, or swipe up to dismiss it. History caps at 1,200 entries. Startup logs include timestamp, bundle ID, game/app version, iOS version, and hardware model.

## Downloads

- [Latest iOS dylib](Latest/SimpleXDumper-v1.3.1.dylib)
- [Latest rootless package](Latest/SimpleXDumper.deb)
- [Archived v1.3.0 dylib](Archive/v1.3.1/SimpleXDumper-v1.3.1.dylib)
- [Archived v1.3.0 package](Archive/v1.3.1/SimpleXDumper.deb)
- [v1.3.0 changelog](Archive/v1.3.1/CHANGELOG.md)
- [Previous v1.2.2 archive](Archive/v1.2.2/)
- [Previous v1.2.0 archive](Archive/v1.2.0/)
- [Previous v1.1.0 archive](Archive/v1.1.0/)
- [Previous v1.0.0 archive](Archive/v1.0.0/)

## Engine support

| Engine | Status | What it does |
| --- | --- | --- |
| Unreal Engine 4 | Supported when runtime layout/profile matches | object/name discovery, reflection dump, C++ SDK, .usmap, IDA/Ghidra mappings, Dumpspace JSON |
| Unity IL2CPP | Live runtime dumper plus a format-detected legacy metadata-v23 fallback; runtime validation remains required | live assemblies/classes/fields/methods and RVAs; metadata-only image/type/member names and indices when live enumeration is unavailable |
| Unity Mono | Not supported | no Mono runtime backend |
| Other engines | Unsupported for engine dumping | generic Game File Manager remains available |

Android isn't supported.

## Unity metadata compatibility

When live IL2CPP exports or domain enumeration are unavailable, a readable legacy metadata-v23 file can still produce `Metadata/ManagedIndex.json` and `ManagedIndex.txt`. These contain image, type, field, method, parameter and property names plus metadata indices. This fallback does not supply native method addresses, runtime type resolution or live field offsets; those require a compatible binary/registration layout or successful live enumeration.

## Compatibility

- Platform: iOS only
- Architecture: arm64
- Deployment target: iOS 14.0+
- Package: rootless Theos .deb plus matching dylib
- Package ID: `com.simplex.simplexdumper` (kept for upgrades)
- Standalone dylib filename: `SimpleXDumper-v1.3.1.dylib` (versioned to distinguish releases).
- The rootless `.deb` keeps the installed loader filename `SimpleXDumper.dylib` for compatibility.

## Contact

Contact / credit link: https://discord.gg/Kr2pvPfEUR
