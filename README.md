# jsScraper

> 🔍 A powerful Python-based tool to extract, filter, and archive JavaScript files (external & inline) from websites. Designed for bug bounty hunters, security researchers, and digital analysts.

---

## 🚀 Overview

**jsScraper** automates the process of collecting and analyzing JavaScript files from websites using **Playwright** and **asynchronous scraping**. It supports inline and external JS extraction, filtering of known libraries, crawling, cross-origin detection, deduplication, and verbose logging.

---

## ⚙️ Features

| Feature                   | Description                                               |
| ------------------------- | --------------------------------------------------------- |
| 📂 External JS Collection | Downloads all loaded `.js` files on a page                |
| 🧠 Inline Script Parsing  | Extracts inline `<script>` tags from HTML                 |
| ✂️ Filtering Engine       | Removes common tracking/analytics and libraries via regex |
| 🔄 Deduplication          | Avoids saving duplicate scripts using SHA-256 hash        |
| 🌐 Crawling               | Follows internal links up to a defined depth              |
| 🏁 Cross-Origin Capture   | Optionally includes third-party JavaScript                |
| 🩵 Logging                | Clean console output & full logs in `verbose.log`         |
| 🧪 Batch Mode             | Accepts URL lists for bulk scraping                       |
| 🔐 Privacy-Aware          | Skips known sensitive or privacy-invasive patterns        |

---

## 🛠️ Requirements

* Python 3.8+

### Dependencies

```txt
playwright
validators
beautifulsoup4
```

Install with:

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

### ⟲ Batch Mode

```bash
python jsScraper.py --url-file urls.txt
```

### ⚙️ Full Configuration

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

## 🗒 CLI Options

| Argument         | Description                                    |
| ---------------- | ---------------------------------------------- |
| `url`            | Target site (e.g., `https://site.com`)         |
| `--url-file`     | Path to file with list of targets              |
| `-o, --output`   | Output directory (default: `getJsOutput`)      |
| `--filter`       | `strict` (default) or `relaxed` JS filtering   |
| `--min-size`     | Minimum script size in bytes (default: 150)    |
| `--crawl`        | Enable internal link crawling                  |
| `--max-depth`    | Crawl depth (default: 2)                       |
| `--cross-origin` | Include third-party JS                         |
| `--clear`        | Clear output directory before execution        |
| `-t, --timeout`  | Page timeout in seconds (default: 60)          |
| `-r, --delay`    | Delay between downloads (default: 0.5s)        |
| `-v, --verbose`  | Log detailed scraping process to `verbose.log` |

---

## 📁 Output Structure

Scripts are saved under:

```
<output_dir>/<domain>/<filter_mode>/
  ├── 001_example_com_main_f3ab23d4.js
  ├── 002_example_com_inline_1a2b3c4d.js
  └── verbose.log
```

Each file is named using:

* Index
* Domain
* Path type (main/inline)
* Content hash (SHA-256, first 8 chars)

---

## 🧐 Use Cases

### 🔐 Security Research

* Find hardcoded secrets or API endpoints
* Identify old/vulnerable JS libraries
* Enhance bug bounty and recon workflows

### 📏 Forensics / Web Archiving

* Capture JavaScript snapshots from any point in time
* Investigate suspicious scripts used in past attacks

---

## 📊 Filtering Modes

* **strict**: Filters out analytics, libraries, known CDNs
* **relaxed**: Allows more scripts through (e.g., UI plugins)

> You can customize patterns in `UNINTERESTING_JS_STRICT` and `UNINTERESTING_JS_RELAXED` inside the code.

---

## 📦 requirements.txt

```txt
playwright
validators
beautifulsoup4
```

---

## 🛡 License

This project is licensed under the **MIT License**. See the `LICENSE` file for details.

---

## 🤝 Contributing

Your ideas and pull requests are welcome!

Planned ideas:

* Secrets detection plugin
* JavaScript beautifier / deobfuscator
* JSON summary reporting
* Docker container support

---

## 👨‍💻 Author

Built with ❤️ by [249BUG](https://github.com/exe249) for security professionals and researchers.
