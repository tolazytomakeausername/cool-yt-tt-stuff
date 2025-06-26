Heyyyy!!! Wazzzupp!!! First non ai generated readme! (mostly cause it was doing a bs job for this one)
So, yeah, yt downloader!
**Disclaimer:** This tool is for personal use only. I’m not responsible if someone uses it to break any rules or laws.
Also, for this tut, I am using DEBIAN. I don't know if all the commands will work on other OSes.

Dependencies:


yt-dlp
google-api-python-client
python-dotenv
ffmpeg
Python 3.6 or higher
isodate


```pip install yt-dlp google-api-python-client python-dotenv isodate```


Install ffmpeg with ```sudo apt install ffmpeg``` for debian, or ```brew install ffmpeg``` for macOS
For windows, idfk gfy.


What ts does is let you download any yt video or playlist from youtube as audio, or audio and video!!! Cool, right? Oh, it's not cool? FUCK OF-
Anyways, whatchu wanna do first is go to the latest release and download the one called "yt" 
Now that you have that, you gonna go to wherever it is, and then if you're on linux debian, do ```chmod +x yt+tt``` And no output = should've worked 
You gotta go to "https://console.cloud.google.com/apis/library/youtube.googleapis.com?authuser=1&inv=1&invt=Ab08Sg&supportedpurview=project" and click enable, then go to "credentials" and then click "create credentials" click "API key" click generate. Copy the API key and then go to where you put yt file and then create a new file called .env

How to make a .env file (Skip if you know how)

1. Install nano. ```sudo apt install nano``` on Debian.
2. ```nano .env```
3. type `YOUTUBE_API_KEY=yourapikeyhere` (Replace with your actual API key)
4. do ```CTRl + O``` ```ENTER``` ```CTRL + X```


***IMPORTANT!!! DO NOT SHARE API KEY WITH ANYONE!!!!! THIS CAN BE USED TO IMPERSONATE YOU AND CAUSE FRAUD. DO NOT SHARE!!!!!!!***


Anyways... Now, you want to do yt -h. If shit pops up, you chillin. If shit doesn't popup, you not. If you're not chilling, dm me on discord with your issue. My discord is "thattrandombird"
