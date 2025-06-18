# jsScraper

> 🔍 A comprehensive, Python-based JavaScript scraping and archiving tool built on Playwright. Designed for security researchers, bug bounty hunters, developers, and analysts to extract, filter, and save JavaScript files (external & inline) from any target website.

---

## 🚀 Overview

**jsScraper** allows you to scan web pages for JavaScript files — both external and inline — and archive them with options to:

- Filter out common libraries and tracking scripts
- Deduplicate using SHA-256 hashes
- Crawl internal pages
- Collect cross-origin resources (optional)
- Generate verbose output logs
- Process entire URL lists

Its powerful combination of **asynchronous scraping**, **Playwright automation**, and **smart filtering** makes it suitable for recon, compliance, forensics, and competitive intelligence.

---

## ⚙️ Features

| Feature                  | Description                                                                 |
|--------------------------|-----------------------------------------------------------------------------|
| 📂 External JS Collection | Captures all loaded `.js` files on target page                              |
| 🧠 Inline Script Parsing  | Extracts `<script>` blocks from HTML content                                |
| ✂️ Filtering Engine       | Removes tracking scripts, analytics, and known libraries using regex        |
| 🔄 Deduplication          | Saves only unique scripts based on SHA-256 hash                             |
| 🌐 Crawling               | Optional crawling of internal links up to specified depth                   |
| 🏁 Cross-Origin Capture   | Capture JS from third-party domains if required                             |
| 🪵 Logging                | Verbose log file (`verbose.log`) and clean CLI logging                      |
| 🧪 Batch Mode             | Accepts a list of target URLs from file                                     |
| 🔐 Privacy-Aware          | Skips sensitive patterns & analytics tools (e.g., GA, Segment, Hotjar)      |

---

## 🧰 Requirements

- Python 3.8+
- Dependencies:
  - `playwright`
  - `validators`
  - `beautifulsoup4`

### Installation

```bash
pip install -r requirements.txt
playwright install
```

---

## 🧪 Usage Examples

### 📄 Basic Usage

```bash
python jsScraper.py https://example.com
```

### 🔁 From URL File

```bash
python jsScraper.py --url-file urls.txt
```

### ⚙️ Full Options

```bash
python jsScraper.py https://example.com \
  --output output_dir \
  --filter strict \
  --min-size 200 \
  --crawl \
  --max-depth 2 \
  --cross-origin \
  --clear \
  --verbose
```

---

## 🧾 CLI Arguments

| Argument         | Description                                                           |
| ---------------- | --------------------------------------------------------------------- |
| `url`            | Target website to scrape (e.g., [https://site.com](https://site.com)) |
| `--url-file`     | Path to file with list of URLs (overrides `url`)                      |
| `-o, --output`   | Output directory (default: `getJsOutput`)                             |
| `--filter`       | Filtering mode: `strict` (default) or `relaxed`                       |
| `--min-size`     | Minimum file size in bytes (default: 150)                             |
| `--crawl`        | Enable crawling of internal links                                     |
| `--max-depth`    | Max depth for crawling (default: 2)                                   |
| `--cross-origin` | Include third-party JS                                                |
| `--clear`        | Clear output folder before writing new data                           |
| `-t, --timeout`  | Page timeout in seconds (default: 60)                                 |
| `-r, --delay`    | Delay between downloads in seconds (default: 0.5)                     |
| `-v, --verbose`  | Enable verbose logging (saved to `verbose.log`)                       |

---

## 📁 Output Structure

Files are saved as:

```
<output_dir>/<domain>/<filter_mode>/
  ├── 001_example_com_main_f3ab23d4.js
  ├── 002_example_com_inline_1a2b3c4d.js
  ├── ...
  └── verbose.log
```

Each JS file is uniquely named using:

* Index
* Domain
* Path
* Content hash (SHA-256, first 8 chars)

---

## 🧠 Use Cases

### 🔐 Security Research

* Extract inline secrets, endpoints, or tokens
* Identify outdated/vulnerable JS libraries
* Use in bug bounty / recon workflows


### 🧾 Web Archiving / Forensics

* Archive all JS on a domain for future analysis
* Identify scripts used in past attacks or shady behavior

---

## 📋 Filtering Modes

* **strict**: Blocks most common analytics, CDNs, libraries
* **relaxed**: Allows more JS through (themes, plugins, etc)

Custom patterns can be added to `UNINTERESTING_JS_STRICT` and `UNINTERESTING_JS_RELAXED` in the script.

---

## 📦 requirements.txt

```txt
playwright
validators
beautifulsoup4
```

---

## 🛡 License

**MIT License** — Free to use, modify, and redistribute. See `LICENSE` for details.

---

## 🤝 Contributing

Pull requests and feature requests are welcome!

Ideas:

* Plugin engine (e.g., secrets detection)
* JS beautification/deobfuscation
* JSON summary report
* Docker wrapper

---

## 👨‍💻 Author

Developed by **[249BUG](https://github.com/exe249)** — built for recon professionals, security analysts, and digital investigators.
