# yt-tt-downloader

## Description
`yt-tt-downloader` is a versatile command-line tool, implemented as a single Python script (`media.py`), designed to simplify downloading video and audio content from both YouTube and TikTok. It leverages `yt-dlp` for the core download functionality and the YouTube Data API for advanced YouTube features like search and playlist handling.

## Features
* **YouTube (`yt`) Subcommand:**
    * **Modes:**
        * Download videos up to 1080p60fps with lossless remuxing (`-v`).
        * Download audio only, preserving the best available audio quality without re-encoding (`-m`).
    * **Content Types:**
        * Search for and download individual YouTube videos or entire playlists.
        * Directly download from a given YouTube video or playlist URL.
    * **Search & Filtering:**
        * Option to search specifically for playlists (`-p`) or videos (`-c`).
        * Interactive prompt to filter search results by minimum and/or maximum video length in seconds (`-j`).
    * **Result Management:**
        * Select specific items for download by 1-based index (e.g., `1,3,5`) or a range (e.g., `4-8`).
        * Shuffle (`-s`) or reverse (`-r`) the order of listed results.
        * Select all items (`-a`), overriding index filters.
        * List results only (`-l`), preventing automatic download even with the `-d` flag.
* **TikTok (`tt`) Subcommand:**
    * **Modes:**
        * Download TikTok videos (`-v`).
        * Download TikTok audio only (`-m`), typically converted to MP3.
    * Requires a direct TikTok video URL for download.
* **Flexible Output:** All downloaded media is saved to a configurable directory (`/mnt/chromeos/MyFiles/offline_stuff` by default).

## Requirements
* Python 3.6 or higher
* `yt-dlp` (`pip install yt-dlp`)
* `google-api-python-client` (`pip install google-api-python-client`) — required for Youtube and playlist functionality.
* `python-dotenv` (`pip install python-dotenv`) — for loading the YouTube API key from an environment file.
* `isodate` (`pip install isodate`) — for parsing video durations.
* **FFmpeg** — an external tool essential for video merging (e.g., combining video and audio streams) and audio extraction. Ensure it's installed and accessible in your system's PATH.

## Setup
1.  **Clone or download this repository:**
    ```bash
    git clone [https://github.com/your-username/yt-tt-downloader.git](https://github.com/your-username/yt-tt-downloader.git) # Replace with your actual repo URL
    cd yt-tt-downloader
    ```
    (If you only have `media.py`, place it in your desired project directory.)

2.  **Install Python dependencies:**
    ```bash
    pip install yt-dlp google-api-python-client python-dotenv isodate
    ```

3.  **Obtain a YouTube Data API v3 key:**
    * Follow the instructions on the [Google Cloud Console](https://console.cloud.google.com/apis/credentials) to get a YouTube Data API v3 key.

4.  **Create a `.env` file:**
    * In the same directory as `media.py`, create a file named `.env`.
    * Add your YouTube API key to this file:
        ```dotenv
        YOUTUBE_API_KEY="YOUR_API_KEY_HERE"
        ```

## Usage

The script is executed using `python media.py` followed by the subcommand and its arguments.

### General Help
To see the full help message:
```bash
python media.py -h
