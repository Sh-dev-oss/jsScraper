# jsScraper 🕷️

![GitHub release](https://img.shields.io/github/release/Sh-dev-oss/jsScraper.svg) ![License](https://img.shields.io/badge/license-MIT-blue.svg)

## Overview

**jsScraper** is a powerful tool designed to extract, filter, and archive inline and external JavaScript files at scale. Built using Python and Playwright, it serves bug bounty hunters, security analysts, and OSINT researchers. With features like crawling, cross-origin scraping, smart filtering, and SHA-256 deduplication, it provides a comprehensive solution for anyone involved in web security and digital forensics.

## Table of Contents

- [Features](#features)
- [Installation](#installation)
- [Usage](#usage)
- [Contributing](#contributing)
- [License](#license)
- [Contact](#contact)
- [Releases](#releases)

## Features

- **Extract JavaScript Files**: Efficiently gather both inline and external JavaScript files from web pages.
- **Filter Content**: Use smart filtering options to focus on relevant scripts based on your needs.
- **Archive Data**: Save extracted data for future analysis or reporting.
- **Crawling Capabilities**: Navigate through websites to find all linked JavaScript files.
- **Cross-Origin Scraping**: Overcome restrictions to scrape content from different domains.
- **SHA-256 Deduplication**: Ensure that duplicate scripts are identified and handled properly.

## Installation

To get started with jsScraper, follow these steps:

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/Sh-dev-oss/jsScraper.git
   cd jsScraper
   ```

2. **Install Dependencies**:
   Ensure you have Python 3 installed. Then, install the required packages:
   ```bash
   pip install -r requirements.txt
   ```

3. **Set Up Playwright**:
   Install Playwright browsers by running:
   ```bash
   playwright install
   ```

## Usage

To run jsScraper, execute the following command in your terminal:

```bash
python jsScraper.py [options] <url>
```

### Options

- `-o, --output`: Specify the output directory for archived files.
- `-f, --filter`: Apply filters to include or exclude specific scripts.
- `-d, --deduplicate`: Enable SHA-256 deduplication to avoid duplicates.

### Example

To extract JavaScript files from a website and save them to a directory called `output`, use:

```bash
python jsScraper.py -o output https://example.com
```

## Contributing

We welcome contributions to jsScraper. If you have ideas for improvements or new features, please follow these steps:

1. Fork the repository.
2. Create a new branch: `git checkout -b feature/YourFeature`.
3. Make your changes and commit them: `git commit -m 'Add some feature'`.
4. Push to the branch: `git push origin feature/YourFeature`.
5. Open a pull request.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Contact

For questions or suggestions, feel free to reach out to the maintainer:

- **Name**: [Your Name]
- **Email**: [your.email@example.com]

## Releases

To download the latest release, visit [here](https://github.com/Sh-dev-oss/jsScraper/releases). Make sure to download the necessary files and execute them as per the instructions provided in the documentation.

For more details on the updates and features in each release, check the [Releases](https://github.com/Sh-dev-oss/jsScraper/releases) section of this repository.

## Topics

This repository covers a wide range of topics relevant to cybersecurity and web scraping:

- **Bug Bounty**: Tools and techniques for identifying vulnerabilities.
- **Cybersecurity**: Protecting systems and networks from digital attacks.
- **Digital Forensics**: Analyzing data from computers and networks.
- **Ethical Hacking**: Authorized testing to identify security weaknesses.
- **Information Security (Infosec)**: Safeguarding data and systems.
- **JavaScript**: The primary language for web development.
- **Open Source Intelligence (OSINT)**: Gathering information from publicly available sources.
- **Penetration Testing (Pentesting)**: Simulating attacks to test security.
- **Playwright**: A Node.js library for browser automation.
- **Python 3**: The programming language used for this project.
- **Recon**: Gathering information about a target.
- **Script Analysis**: Examining scripts for vulnerabilities.
- **Security Tools**: Various tools for enhancing security.
- **Web Security**: Protecting websites from threats.
- **Web Scraper**: Tools for extracting data from web pages.

## Conclusion

jsScraper is a versatile tool that empowers security professionals and researchers. By streamlining the process of extracting and analyzing JavaScript files, it enhances your ability to identify vulnerabilities and gather intelligence. 

Explore the features, contribute to the project, and stay updated with the latest releases to maximize your web security efforts. 

For further information, visit the [Releases](https://github.com/Sh-dev-oss/jsScraper/releases) section for the latest updates and downloads.