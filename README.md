# yt-tt-downloader

## Description
`yt-tt-downloader` is a powerful command-line tool, implemented as a single executable Python script named `yt`, designed to streamline the process of downloading video and audio content from both YouTube and TikTok. It leverages `yt-dlp` for core download functionality and integrates with the YouTube Data API for advanced features like intelligent search, playlist handling, and video duration filtering.

## Quick Start
Follow these steps to get `yt-tt-downloader` up and running quickly:

1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/tolazytomakeausername/cool-yt-tt-stuff.git](https://github.com/tolazytomakeausername/cool-yt-tt-stuff.git)
    cd cool-yt-tt-stuff
    ```
2.  **Make the script executable:**
    ```bash
    chmod +x yt
    ```
3.  **Install Python dependencies:**
    ```bash
    pip install yt-dlp google-api-python-client python-dotenv isodate
    ```
4.  **Obtain a YouTube API Key** and save it in a `.env` file (see "Setup" section for details).
5.  **Install FFmpeg** (essential for video processing - see "Requirements" for details).
6.  **Start downloading!**
    * **YouTube example (download audio):** `yt yt "lofi hip hop" -m -d`
    * **TikTok example (download video):** `yt tt https://www.tiktok.com/@user/video/1234567890 -v -d`

For more detailed instructions and advanced options, please refer to the sections below.

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
* **Python 3.6 or higher**
* **Python Libraries:**
    * `yt-dlp` (`pip install yt-dlp`)
    * `google-api-python-client` (`pip install google-api-python-client`) — required for Youtube and playlist functionality.
    * `python-dotenv` (`pip install python-dotenv`) — for loading the YouTube API key from an environment file.
    * `isodate` (`pip install isodate`) — for parsing video durations.
* **FFmpeg**: An external tool crucial for video merging (e.g., combining video and audio streams) and efficient audio extraction. Please ensure FFmpeg is installed on your system and accessible in your system's PATH. You can usually install it via your operating system's package manager (e.g., `sudo apt install ffmpeg` on Debian/Ubuntu, `brew install ffmpeg` on macOS).

## Setup
1.  **Clone the repository:**
    Open your terminal and clone the project:
    ```bash
    git clone [https://github.com/tolazytomakeausername/cool-yt-tt-stuff.git](https://github.com/tolazytomakeausername/cool-yt-tt-stuff.git)
    cd cool-yt-tt-stuff
    ```
    *(If you only have the `yt` script file, place it in your desired project directory.)*

2.  **Rename the script (if necessary):**
    If the downloaded script is named `media.py`, rename it to `yt` for direct execution:
    ```bash
    mv media.py yt
    ```

3.  **Make the script executable:**
    Grant execute permissions to the `yt` script:
    ```bash
    chmod +x yt
    ```

4.  **Install Python dependencies:**
    Navigate to the project directory (if you're not already there) and install the required Python packages:
    ```bash
    pip install yt-dlp google-api-python-client python-dotenv isodate
    ```

5.  **Obtain a YouTube Data API v3 key:**
    * `yt-tt-downloader` uses the YouTube Data API for searching and managing playlists. You'll need an API key from Google.
    * Go to the [Google Cloud Console](https://console.cloud.google.com/apis/credentials).
    * Create a new project (if you don't have one).
    * Enable the "YouTube Data API v3" for your project.
    * Create API credentials (select "API key").

6.  **Create a `.env` file:**
    * In the same directory as your `yt` script, create a new file named `.env`.
    * Add your YouTube API key to this file in the following format:
        ```dotenv
        YOUTUBE_API_KEY="YOUR_API_KEY_HERE"
        ```
        (Replace `"YOUR_API_KEY_HERE"` with the actual key you obtained).

7.  **Optional: Add `yt` to your system's PATH:**
    For convenient execution of the `yt` command from any directory in your terminal, you can move the script to a directory that is already in your system's `PATH` (e.g., `/usr/local/bin` on Linux/macOS):
    ```bash
    sudo mv yt /usr/local/bin/
    ```
    Alternatively, you can add the script's current directory to your `PATH` environment variable.

## Usage

The `yt` script is executed directly from your terminal, followed by the subcommand (`yt` for YouTube or `tt` for TikTok) and its specific arguments.

### General Help
To see the full help message with all available options:
```bash
yt -h
