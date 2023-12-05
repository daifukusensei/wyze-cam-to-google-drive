# Wyze Cam-to-Google Drive
A script used by [wz_mini_hacks](https://github.com/gtxaspec/wz_mini_hacks) on a Wyze Cam to upload motion-detected recordings to Google Drive.

## Why?
Wyze Cams offer the ability to upload video recordings to cloud, but only via paid subscription. This script is used alongside [wz_mini_hacks](https://github.com/gtxaspec/wz_mini_hacks) on a compatible Wyze Cam to instead upload to a Google Drive account at no additional cost.

## Requirements
- Wyze Cam with [wz_mini_hacks](https://github.com/gtxaspec/wz_mini_hacks) installed. I use a Wyze Cam Pan v2
- Google Drive account with [API access enabled](https://medium.com/@ianhutch90/google-drive-file-upload-using-the-terminal-3652ee90a6f6)
- Motion-detection enabled

## Setup instructions
1. Get [wz_mini_hacks](https://github.com/gtxaspec/wz_mini_hacks) up-and-running on a compatible Wyze Cam
2. Enable API access to your Google Drive account, making note of the *client ID*, *client secret* and *refresh token*. For reference:
    - [Google Drive File Upload Using The Terminal](https://medium.com/@ianhutch90/google-drive-file-upload-using-the-terminal-3652ee90a6f6)
    - [Curl with google drive](https://medium.com/@hoon33710/curl-with-google-drive-9cdc21e45bc8)
3. Download this repository's script and update the following variables, values enclosed in quotes:
    - `CLIENTID`
	- `CLIENTSECRET`
	- `REFRESHTOKEN`
	- `RECORDINGDIR`
4. Copy the updated script to *wz_mini/etc/rc.local.d* on the Wyze Cam's microSD card
5. Boot, and new motion-detected recordings will be uploaded to the root of your Google Drive in the naming-convention of `YYYYMMDD-HHMM.mp4`

## Disclaimer
**Use at your own risk.** It's bad practise to hard-code credentials in a script, though the light-weight BusyBox Linux environment used by [wz_mini_hacks](https://github.com/gtxaspec/wz_mini_hacks) made implementation of service accounts challenging. Thus, a Google account dedicated for use by this script is preferred.