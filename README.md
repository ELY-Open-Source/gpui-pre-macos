# gpui-pre-macos

crates.io's `gpui-pre-macos` 0.3.8 with one change for ELYTerminal, which takes it through `[patch.crates-io]`.

gpui's `ClipboardItem` holds text, an image and files together, and the pasteboard wrote one of them at most: two entries went as their text alone, and files never went. kitty's clipboard protocol, OSC 5522, writes and reads them together. The pasteboard now writes every entry, files as file URLs, each its own pasteboard item, text and images on the first; and reads every kind it holds: its files, its text and the first image format gpui knows.

Remove this fork once a gpui-pre release writes and reads a whole `ClipboardItem` on macOS.
