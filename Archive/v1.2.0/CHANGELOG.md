# SimpleX Toolkit v1.2.0

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
