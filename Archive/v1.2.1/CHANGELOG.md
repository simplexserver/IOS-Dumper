# SimpleX Toolkit v1.2.1

## Unity IL2CPP runtime correction
- Fix the live Unity wrapper initialization order: the wrapper no longer calls the dumper initializer before assigning the final output directory.
- Read the current assembly count directly from the initialized IL2CPP domain, then invoke the dumper once its output paths are established.
- Ensure Script.json is created inside the per-run Dump_<bundle>_<timestamp> directory rather than attempting to open it at the filesystem root.

## Metadata version 39 and menu status follow-up
- Displays the supported engine list on every app, while preserving the unsupported-app status and contact link.
- Adds 31-section triplet header parsing for metadata versions 32–39.
- Validates section offsets, sizes, and counts; preserves raw metadata and exports the metadata string heap.
- Explicitly skips v39 variable-width literal/type/method record decoding in the legacy sidecar.
- Requires IL2CPP thread attach/detach exports for worker-thread enumeration.
- Adds portable tests for v35, v38/v39, malformed headers/sections, and unsupported versions.

## compatibility
- iOS only, arm64, iOS 14.0 deployment target, rootless Theos package.
- Preserves the package identifier com.simplex.simplexdumper and the existing SimpleXDumper binary filenames.
- Unity IL2CPP remains subject to runtime export availability and on-device validation; Unity Mono and Android remain unsupported.

---

## UI and app detection
- Restore the original paw floating toggle instead of the ant icon.
- Preserve the draggable/pulse toggle behavior and existing bounce/fade menu animations.
- Keep the UE4 dumper interface and output controls.
- Remove the loaded Mach-O inventory view; restrict the UE4 module picker to the main executable and likely Unreal modules instead of every loaded image.
- Simplify the menu text to the detected engine/unsupported state, supported engine families, and the clickable Discord contact link.
- Keep Logs and Files available for output diagnostics and sharing.

## Unity IL2CPP
- Integrate a live iOS IL2CPP runtime dumper core adapted under the upstream MIT license.
- Resolve runtime exports from the loaded UnityFramework or libil2cpp image with bounded errors instead of an unbounded dlopen retry loop.
- Enumerate the IL2CPP domain, assemblies, images, classes, fields, properties, methods, parameter signatures, field offsets, and native method pointers.
- Generate combined `Dump.cs`, per-assembly C# declaration files, IDA `Script.json`, `Summary.txt`, and a runtime log.
- Attach the worker thread to IL2CPP when thread-attachment APIs are exported.
- Preserve the existing global-metadata parser as an optional supplemental export rather than presenting it as the main dumper.
- Improve method RVA calculation, C# string literal escaping, UTF-16 conversion, and generic arity formatting.
- Document export/obfuscation/runtime limitations and the need for per-game validation.

## Unreal Engine 4
- Preserve the existing UE4 analyzer, profile system, SDK/mapping outputs, runtime reports, and generation flow.

## compatibility
- iOS only, arm64, iOS 14.0 deployment target, rootless Theos package.
- Existing package identifier `com.simplex.simplexdumper` and SimpleXDumper binary filenames remain unchanged for upgrade compatibility.
- Unity Mono and Android remain out of scope.
- A successful CI build is not a substitute for testing on actual supported game builds.
