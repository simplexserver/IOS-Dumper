# SimpleX Toolkit v1.3.0

## File inspection and app container
- Adds recursive case-insensitive search, result parent paths, name/size/date sorting and size filters.
- Files open directly in the editor. Save remains disabled until the buffer changes, then turns blue.
- Find highlights all case-insensitive matches, reports match count and cycles previous/next.
- Large files remain paged to bound memory.
- Replaces the permanent selection toolbar with long-press Open, Share, Get Info, Rename, Move and Delete actions.
- Adds drag/drop moving into folders.
- The plus control creates a folder or an empty file; the user enters the complete name and extension.
- Adds Game File Manager roots: Game Folder, Documents, Library, Caches, Temporary and App Bundle.
- App Bundle is read-only.
- UE4 and Unity output folders use Dump, then Dump 2, etc. Existing dumps are retained on collisions.

## Compatibility and safety
- iOS only, arm64, iOS 14.0 deployment target, rootless Theos package.
- Existing UE4 and Unity IL2CPP dump paths remain in place.
- Android remains out of scope.
- No IDFV/device identity spoofing or device-enforcement bypass is added.
- CI success is not live device/game validation.
