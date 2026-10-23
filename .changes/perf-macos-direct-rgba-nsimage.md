---
"tray-icon": patch
---

On macOS, build the tray `NSImage` directly from raw RGBA pixels via `NSBitmapImageRep` instead of the PNG encode/decode round-trip, making `set_icon` 34–45% faster. `set_icon` also preserves the configured template mode instead of hardcoding `false`, and `set_icon_as_template` skips re-assigning the image when the flag is unchanged.
