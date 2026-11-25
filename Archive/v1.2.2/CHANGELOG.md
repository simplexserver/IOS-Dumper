# SimpleX Toolkit v1.2.2

## Files browser and inspection
- Folder taps now open folders; file taps open a preview instead of selecting.
- Adds an explicit Select/Done mode with checkboxes and batch Share, Rename, and Delete.
- Adds New Folder and safe in-root rename operations.
- Moves directory enumeration off the UI thread and drops stale scan results after navigation.
- Uses Quick Look for supported media and documents.
- Adds a lightweight monospace source/text viewer.
- Loads large text files in bounded 128 KiB pages to avoid whole-file memory spikes.
- Allows atomic editing and saving only for text files up to 512 KiB; larger files remain paged/read-only.

## Logs console
- Adds All, Dump, Files, Unity, System, and Other filters.
- Adds live search through the native iOS keyboard.
- Exports only the active category/search result through the iOS share sheet.
- Adds outside-tap close, an explicit close control, and swipe-up dismissal.
- Batches table updates and retains the latest 1,200 log entries.
- Emits startup timestamp, bundle ID, app/game version, iOS version, and hardware model after installing the log bridge.
- Synchronizes logger callback snapshots to avoid racing callback installation.

## Compatibility
- iOS only, arm64, iOS 14.0 deployment target, rootless Theos package.
- Preserves package identifier com.simplex.simplexdumper and binary names SimpleXDumper.dylib and SimpleXDumper.deb.
- Preserves the existing UE4 and Unity IL2CPP dump paths, paw toggle, and menu animations.
- Unity Mono and Android remain out of scope.
- CI success is not live validation against every game build.
