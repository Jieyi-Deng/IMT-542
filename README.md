# Bluesky Follower Feed Analyzer

## Overview
This application is a lightweight data pipeline that interacts with the Bluesky Social network via the AT Protocol API. It retrieves structured JSON data to visualize and analyze community activity. Specifically, it fetches a target user's followers and then retrieves the most recent posts authored by those followers. This provides a "follower feed" perspective—allowing you to analyze what the audience of a specific account is currently talking about.

## Instructions
The repository contains a Python Notebook file (`I3-Bluesky.ipynb`) that can be easily executed in Google Colab or any local Jupyter environment.

**How to Run in Google Colab:**
1. Download the notebook file from this repository.
2. Go to [Google Colab](https://colab.research.google.com/).
3. Click `File` > `Upload notebook` and select the downloaded file.
4. Run the cells sequentially by clicking the "Play" button or pressing `Shift + Enter`.

**How to Run Locally:**
1. Ensure you have Python installed along with the `pandas` and `requests` libraries.
2. Open your terminal and start your environment (e.g., `jupyter notebook`).
3. Open the file and execute the cells.

## Code Example
```python
# Example of fetching a user's feed from the public Bluesky API
import requests

base_url = "[https://public.api.bsky.app/xrpc/](https://public.api.bsky.app/xrpc/)"
endpoint = f"{base_url}app.bsky.feed.getAuthorFeed"
response = requests.get(endpoint, params={"actor": "bsky.app", "limit": 10})
data = response.json()