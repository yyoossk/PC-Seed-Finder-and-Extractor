# PC Seed Finder and Extractor
![screenshot](https://github.com/user-attachments/files/31752074/default.bmp)
PC Seed Finder and Extractor is a Windows utility for detecting MArchive seeds directly from supported PC game `.exe` files and extracting `alldata.psb.m` / `alldata.bin` with `MArchiveBatchTool.exe`.

## Features

* Detects MArchive seeds from Windows `.exe` files
* Supports both PE32 / x86 and PE32+ / x64 executables
* Displays the detected seed in a copyable field
* Supports titles without a detectable seed
* Extracts `alldata.psb.m` and `alldata.bin`
* Custom extraction destination
* Drag-and-drop support
* Green progress meter
* Real-time extraction log
* Automatically opens the extracted folder
* Multi-language interface
* High-DPI support
* 32-bit and 64-bit builds available

## Download

https://github.com/yyoossk/PC-Seed-Finder-and-Extractor/releases

Available builds:

* **Standard version** — x86 / 32-bit
* **64-bit version** — x64 / 64-bit

For most modern Windows PCs, the **64-bit version** is recommended.

## Seed Detection

Select or drag and drop the PC game's `.exe` file, then click **Find Seed**.

The application analyzes MArchive-related executable structures and attempts to locate the seed automatically.

Known MArchive strings and code references are used as part of the detection process rather than relying on a fixed list of known seeds.

If only the seed is required, the game `.exe` file is enough.

## Archive Extraction

To extract MArchive data, select:

* The folder containing `MArchiveBatchTool.exe`
* `alldata.bin`
* `alldata.psb.m`
* Extraction destination

Then click **Extract**.

For a normal detected seed, the application performs an operation equivalent to:

```text
MArchiveBatchTool.exe fullunpack --keep alldata.psb.m zlib <SEED> 64
```

## No Seed

If the result is **No Seed**, the title may:

* Originally not use a seed, or
* Use a seed that the current detection method cannot identify

For titles that genuinely do not use a seed, the application can use the No Seed extraction mode:

```text
MArchiveBatchTool.exe fullunpack --keep alldata.psb.m zlib "Illegal function call" 92
```

## Drag and Drop

The following can be dragged directly onto the corresponding fields:

* Game `.exe`
* `alldata.bin`
* `alldata.psb.m`
* MArchiveBatchTool folder
* Extraction destination

Files may be stored in different directories or drives.

## Real-Time Progress and Log

During extraction, the application shows:

* Current processing stage
* Green progress meter
* Real-time output from `MArchiveBatchTool.exe`
* Errors and warnings

The extracted folder is automatically opened after successful completion.

## Language Support

The application automatically selects its language based on the Windows system language.

Supported languages include:

* Japanese
* English
* Simplified Chinese
* Traditional Chinese
* Korean
* German
* French
* Spanish
* Italian
* Portuguese
* Russian

The language can also be changed manually from the **Language** menu.

## Requirements

For seed detection:

```text
Game executable (.exe)
```

For extraction:

```text
Game executable (.exe)
alldata.bin
alldata.psb.m
MArchiveBatchTool.exe
```

## Notes

Seed detection is based on known MArchive initialization and executable-reference patterns.

Support is not guaranteed for every PC game or every MArchive implementation.

Different executable layouts or future implementations may require additional detection support.

## Disclaimer

This tool is intended for research, interoperability, preservation, and analysis of files that you legally own or are authorized to access.

No copyrighted game data is included.
