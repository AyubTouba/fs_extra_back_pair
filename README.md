# fs_extra_back_pair

A fork of [`fs_extra`](https://crates.io/crates/fs_extra), a Rust library for advanced file and directory operations.

This fork adds one key feature:  
➡️ **`path_file` in `TransitProcess`** — to track the exact file being copied during progress updates.  
Useful in apps (like Tauri) where monitoring nested file paths is required.

---

## 🔧 Installation

In your `Cargo.toml`:

```toml
[dependencies]
fs_extra_back_pair = { git = "https://github.com/AyubTouba/fs_extra_back_pair", branch="main" }
```
---

## Example
```rust
let handler = |process_info: TransitProcess| {
    println!("Copying: {:?}", process_info.path_file);
    TransitProcessResult::ContinueOrAbort
};

copy_with_progress(&from, &to, &options, handler)?;
```

## License & Credit
Based on the work of [`@webdesus`](https://github.com/webdesus).
Licensed under MIT or Apache-2.0.
