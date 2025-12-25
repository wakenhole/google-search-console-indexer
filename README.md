# Google Search Console Indexer

This script allows you to index URLs from a sitemap using the Google Indexing API. It supports bulk indexing and provides a dry-run mode for testing.

## Prerequisites

- Python 3.6+
- A Google Cloud Service Account with the **Indexing API** enabled.
- A `key.json` file containing your Service Account credentials in the same directory.
- The Service Account email must be added as an **Owner** in Google Search Console for the property you want to index.

## Installation

Install the required dependencies:

```bash
pip install requests xmltodict google-auth google-api-python-client rich
```

## Usage

### Run Indexing

To fetch URLs from a sitemap and index them:

```bash
python indexer.py <sitemap_url>
```

### Dry Run

To simulate the process without sending actual requests to Google:

```bash
python indexer.py <sitemap_url> --dry-run
```

In dry-run mode, the script will fetch the sitemap and list the URLs but will not call the Indexing API.