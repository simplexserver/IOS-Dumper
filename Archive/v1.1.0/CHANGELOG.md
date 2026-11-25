# SimpleX Toolkit v1.1.0

## product and iOS UI
- Changes the in-app product identity to SimpleX Toolkit and the subtitle to iOS Runtime & Engine Toolkit.
- Shows the floating toolkit entry point in normal UIKit user apps, including unsupported apps.
- Displays detected engine state, supported engine list, tool descriptions, and unsupported-app status.
- Removes the separate Discord / Credits button; the contact URL is clickable in the menu subtitle.
- Adds loaded app Mach-O image inventory and replaces the top-two-largest-framework heuristic with dyld image enumeration.
- Keeps Logs and Files available when the current app has no supported engine.
- Preserves the Debian package identifier and SimpleXDumper tweak filename for in-place upgrades.

## Unreal Engine 4
- Retains the existing UE4 analyzer, layout detection, profile overrides, C++ SDK, mappings, IDA/Ghidra, and Dumpspace pipeline.
- Adds a runtime address report for GNames, GObjects, GEngine, GWorld, and ProcessEvent when discovered.
- Renames the generated log to SimpleXToolkit.log.

## Unity IL2CPP — experimental
- Adds an iOS global-metadata.dat locator for common app-bundle layouts.
- Validates IL2CPP magic, supported metadata version, and string-section bounds before extraction.
- Preserves raw metadata and exports MetadataHeader.txt, MetadataStrings.txt, StringLiterals.txt, and Summary.txt.
- Supports the stable string-table header prefix for versions 16–35; rejects version 38+ rather than guessing at its variable-width layout.
- Does not yet reconstruct complete assemblies, types, methods, fields, native method addresses, or a full Unity SDK.

## compatibility
- iOS only, arm64, iOS 14.0 deployment target, rootless Theos package.
- UE4 compatibility remains dependent on game version, runtime layout, and profile compatibility.
- Unity support is experimental and limited to metadata string extraction.
- Android remains out of scope.