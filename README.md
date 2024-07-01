# Fetching Online Data

This guide provides detailed instructions for fetching online data, including downloading and extracting files from various sources, using Bash commands and Python libraries in a Jupyter notebook.

## Prerequisites

Ensure you have the following packages installed in your environment:
- `requests`
- `gdown`
- `unrar` (for extracting RAR files)

You can install the necessary packages using pip:
```bash
pip install requests gdown
```

## Steps

### 1. Copying Files from Google Drive

First, copy a file from your Google Drive to the local environment using the `cp` command.

```bash
!cp /content/drive/MyDrive/DeepTracker.rar /content/Test.rar
```

### 2. Extracting RAR Files

Use the `unrar` command to extract files from the copied RAR archive.

```bash
!unrar x /content/Test.rar
```

### 3. Installing `gdown`

Install the `gdown` library to download files from Google Drive links.

```bash
!pip install -U gdown
```

### 4. Downloading a File from Google Drive

Use `gdown` to download a file from Google Drive using its shareable link.

```python
import gdown

url = 'https://drive.google.com/file/d/1wMuBz2JvmASUVOEbKDLqRwedTv_3eWHo/view?usp=sharing'
output = 'image.jpg'
gdown.download(url, output, quiet=False)
```

### 5. Downloading a File Using `requests`

Use the `requests` library to download a file from a given URL.

```python
import requests

url = 'http://vision.soic.indiana.edu/egohands_files/egohands_data.zip'
response = requests.get(url)
with open('egohands_data.zip', 'wb') as file:
    file.write(response.content)
```
