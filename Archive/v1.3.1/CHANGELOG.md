# SimpleX Toolkit v1.3.1

## IL2CPP metadata compatibility
- Adds a format-detected legacy metadata-v23 index for compatible IL2CPP metadata files, independent of application or game title.
- Exports image, type, field, method, parameter and property metadata to ManagedIndex.json and ManagedIndex.txt.
- Validates fixed-width record tables, string references, image/type ranges and member/parameter slices before exporting.
- Rejects malformed metadata ranges without losing the original metadata and string export.
- Adds metadata-only fallback when live Unity runtime exports, domain initialization or thread attachment are unavailable.
- Keeps live runtime enumeration as the preferred full dump; metadata-only output does not claim native addresses, resolved runtime type signatures or field offsets.
- Adds synthetic v23 fixtures plus malformed-range regression coverage alongside the existing v35/v38/v39 tests.
- Adds MIT attribution for the legacy metadata schema component.

## Compatibility
- iOS only, arm64, iOS 14.0 deployment target, rootless Theos package.
- Preserves package identifier com.simplex.simplexdumper.
- Standalone release dylib is versioned as SimpleXDumper-v1.3.1.dylib; the installed package retains its stable loader filename.
- Existing UE4 and live Unity dump paths, paw toggle, and menu animations are preserved.
- Android and Unity Mono remain out of scope.
- CI success does not replace on-device testing against each target runtime.
