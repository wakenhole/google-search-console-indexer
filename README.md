# Google Search Console Indexer

This script allows you to index URLs from a sitemap using the Google Indexing API. It supports bulk indexing and provides a dry-run mode for testing.

## Prerequisites

- Python 3.6+
- A Google Cloud Service Account with the **Indexing API** enabled.
- A `key.json` file containing your Service Account credentials in the same directory.
- The Service Account email must be added as an **Owner** in Google Search Console for the property you want to index.
  
### 1. Clone the Repository

First, clone this repository to your local machine:

```bash
git clone https://github.com/wakenhole/google-search-console-indexer.git
cd google-search-console-indexer
```

### 2. Set Up Google Search Console API

1. Go to the [Google Cloud Console](https://console.cloud.google.com/).
2. Enable the **Indexing API** for your project.
3. Create a **Service Account** and download the JSON key file (`key.json`).
4. Add the service account email to your **Google Search Console property** with **full permissions**.

### 3. Install Dependencies

To run this project, you'll need to install the required Python libraries. You can do this by running:

```bash
pip install -r requirements.txt
```

Alternatively, install them manually:

```bash
pip install google-auth google-auth-oauthlib google-auth-httplib2 google-api-python-client requests xmltodict rich
```

### 4. Usage

#### Run Indexing

To fetch URLs from a sitemap and index them:

```bash
python indexer.py <sitemap_url>
```

####  Dry Run

To simulate the process without sending actual requests to Google:

```bash
python indexer.py <sitemap_url> --dry-run
```

In dry-run mode, the script will fetch the sitemap and list the URLs but will not call the Indexing API.
