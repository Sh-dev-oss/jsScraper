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
