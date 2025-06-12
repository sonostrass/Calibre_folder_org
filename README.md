# 📚 Calibre ➜ Komga Organizer

A 🐍 Python CLI tool that exports and reorganizes a Calibre ebook library into a Komga-friendly folder structure — complete with smart naming, duplicate detection, and dry-run mode.

---

## 🚀 Features

✅ Reads metadata from `metadata.db`  
📂 Builds a clean Komga-compatible folder structure  
🔢 Formats tome numbers (`T01`, `T001.25`, etc.)  
🧠 Automatically distinguishes series vs one-shots  
🌀 Only copies files if updated (or new)  
⚠️ Handles duplicate conflicts into `_ERROR` folders  
📝 Clean logging (`INFO`, `DEBUG`, `ERROR`)  
🔍 Optional filtering by last-modified datetime  
🧪 Supports dry-run mode for previewing changes  

---

## 📁 Output Structure

### 📚 Series:
```
/output/F/Foundation/
  T01 - Foundation.epub
  T02 - Foundation and Empire.epub
```

### 📘 One-shots:
```
/output/B/_oneshots B/
  Mist (S. Author).epub
```

> ℹ️ Komga detects one-shots automatically if folder name includes `_oneshots`.

### ❗ Duplicates:
```
/output/_ERROR/F/Foundation/T02 - Foundation and Empire [DUPLICATE].epub
```

---

## 🧪 Usage

```bash
python main.py   --calibre-db "/path/to/metadata.db"   --output "/path/to/export"   [--dry-run]   [--since-date "YYYY-MM-DDTHH:MM:SS"]   [--log-dir "./logs"]   [--verbose]   [--error-dir "/your/path/_ERROR"]
```

### Example:
```bash
python main.py   --calibre-db "~/Calibre Library/metadata.db"   --output "~/KomgaLibrary"   --since-date "2025-06-12T00:00:00"   --verbose
```

---

## 🧰 Project Structure

| File            | Description                             |
|-----------------|-----------------------------------------|
| `main.py`       | CLI entry point                         |
| `config.py`     | Default paths and settings              |
| `chemin.py`     | Computes destination paths              |
| `copier.py`     | Conditional copy with date handling     |
| `tome_format.py`| Tome number formatting logic            |
| `utils.py`      | String normalization and prefix logic   |

---

## 🔐 Requirements

- Python 3.7+
- No external dependencies (pure standard library)

---

## 🗒️ Tips

- Use `--dry-run` to simulate the export process
- Enable `--verbose` for detailed logs
- Komga will automatically generate thumbnails from embedded EPUB covers

---

## 🧡 License

MIT — free for personal and commercial use.

---

## 🛠️ Maintainer

Made with ☕ and 🤖 by [YourNameHere]
