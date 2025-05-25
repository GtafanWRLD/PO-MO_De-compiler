# PO File Merger

A Python tool to batch-merge `.po` translation files for Mir Tankov (and other games).  
It syncs English and Russian `.po` files by always **replacing Russian translations with their English counterparts** where available, preserving unmatched Russian entries.

---

## Features

- Processes all `.po` files from a `ru` (Russian) folder.
- For each Russian file:
  - If a matching English file exists in the `en` folder, Russian translations are replaced with the English ones (`msgstr`).
  - If no English file is found, the Russian file is copied unchanged.
- Output files always retain the Russian filename and are saved to a `merged` folder.
- English files that do **not** have a Russian original are skipped (with a warning message).
- **All required folders** (`en`, `ru`, `merged`) are created automatically if missing.
- Provides clear terminal output about what actions were taken for each file.

---

## Usage

### 1. Prepare your folders and files

Place your Russian `.po` files in a folder named `ru`.  
Place your English `.po` files in a folder named `en`.  
You do **not** need to create the `merged` folder; the script will create it automatically if it doesn't exist.

Your folder structure should look like this:

```
project_folder/
│
├── merge_po_files.py
├── en/
│   ├── yourfile.po
│   └── ...
├── ru/
│   ├── yourfile.po
│   └── ...
```

### 2. From your project folder, run:

```sh
python merge_po_files.py
```

#### Example Output

```
account_dashboard.po: Merged, replaced 24 entries.
settings.po: English version of the file not found. Copied Russian file as-is.
user_profile.po: Russian version of the file not found. Skipped, no file saved in merged.
Done! All merged files saved in 'merged' folder.
```

---

## Edge Cases

- If a file exists in `ru/` but **not** in `en/`, it is copied unchanged to `merged/`.
- If a file exists in `en/` but **not** in `ru/`, it is skipped—no file will appear in `merged/`, and a warning is printed.
- All folders (`en`, `ru`, `merged`) are created if missing, so you never get a "folder not found" error.
- The script detects and warns if it finds a possible language mismatch (e.g., if an "English" file appears to contain Russian or vice versa).

---

## Requirements

- Python 3.x
- [polib](https://pypi.org/project/polib/)
- [langdetect](https://pypi.org/project/langdetect/)

Install dependencies with:

```sh
pip install polib langdetect
```

---

## License

MIT License.  
Feel free to modify or adapt for your own workflow!
