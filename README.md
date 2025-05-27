# PO/MO File Converter Tool

A command-line Python tool for converting between `.mo` and `.po` translation files, commonly used in software localization (such as with GNU gettext). This tool can both **compile** `.po` files into `.mo` binaries and **decompile** `.mo` files back into `.po` files.

---

## 🔧 Features

- **Decompile**: Converts all `.mo` files in a folder to `.po` files.
- **Compile**: Converts all `.po` files in a folder to `.mo` files.
- Automatic folder creation for output (`/compiled` or `/decompiled`).

---

## 🚀 Usage

1. Run the script:
   ```bash
   python converter.py
   ```

2. Choose the desired operation:
   - 1 = Decompile `.mo` files to `.po`
   - 2 = Compile `.po` files to `.mo`

3. Enter the path to the folder containing your source files.

4. Done! Output files will be saved in `/compiled` or `/decompiled` folder next to the script.

---

## 📁 Output Structure

```
project_root/
│
├── converter.py
├── compiled/      ← compiled .mo files
└── decompiled/    ← decompiled .po files
```

---

## ✅ Dependencies

- `polib` - A Python library to handle `.po` and `.mo` files

Install with:

```bash
pip install polib
```

---

## 📌 Notes

- Handles batch processing for all files in the given folder.
- If no `.po` or `.mo` files are found, it notifies the user.
- Paths with spaces are supported if enclosed in quotes.

---

## 📝 Recent Changes

- 🔄 Full rewrite with interactive CLI (no args required)
- 🔒 Added error handling and input validation
- 📁 Organized output into structured folders
- 🧠 File type detection logic cleaned up

---

## 📃 License

MIT License.
