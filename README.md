# Local .7z Compressor (No Upload)

A fast, privacy-focused web application that compresses files and folders directly into `.7z` archives inside your browser using WebAssembly—no server uploads required.

**Live Demo:** [https://747-glitch.github.io/7zip-compresser/](https://747-glitch.github.io/7zip-compresser/)

---

## Features

- **100% Client-Side & Private:** All compression happens locally in your browser's memory using WebAssembly. Files never leave your device.
- **Drag & Drop + Folder Support:** Drag and drop individual files, multiple files, or entire nested folders while preserving the directory structure inside the `.7z` archive.
- **Smart Archive Naming:** Automatically names the output `.7z` file based on your uploaded file or root folder name (with full support for custom filenames).
- **Adjustable Compression Levels:** Choose from 6 levels ranging from `0 - Store` (fastest, no compression) to `9 - Ultra` (smallest size).
- **Real-Time Progress & Stats:** Tracks engine initialization, file loading, and 7-Zip compression progress, then displays elapsed time and before/after file size savings.
- **Dark Mode:** Built-in light and dark theme toggle.
- **Chromebook Supported:** Basicly any device that runs chrome and that has a good amount of RAM.

---

## How It Works

This tool runs a WebAssembly build of the 7-Zip command-line engine (`7z-wasm`) directly in the browser:

1. **0% – 5%:** Initializes the 7-Zip WebAssembly engine and fetches the `7zz.wasm` binary.
2. **5% – 20%:** Recreates nested directory structures and writes selected files into virtual WebAssembly memory.
3. **20% – 98%:** Executes 7-Zip compression with the `-bsp1` flag to parse real-time percentage updates to the progress bar.
4. **100%:** Generates a local `.7z` download, displays compression size savings, and releases memory.

---

## Running Locally

Running Locally supported.
Not offline yet

---

## Limitations

- **Browser Memory Limits:** Because files are processed in RAM, compressing very large files or folders (typically over 500 MB–1 GB) may cause the browser tab to run out of memory.
- **Main-Thread Execution:** Compression runs on the main UI thread, which may briefly pause page responsiveness during heavy compression tasks.

---

## Built With

- HTML5, CSS3, and Vanilla JavaScript (ES Modules)
- [7z-wasm](https://github.com/nika-begiashvili/7z-wasm) — WebAssembly port of 7-Zip
- AI
