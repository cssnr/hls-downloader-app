[![Chrome Web Store Version](https://img.shields.io/chrome-web-store/v/mpmiiaolodhanoalpjncddpmnkbjicbo?label=chrome&logo=googlechrome)](https://chromewebstore.google.com/detail/hls-video-downloader/mpmiiaolodhanoalpjncddpmnkbjicbo)
[![Mozilla Add-on Version](https://img.shields.io/amo/v/hls-video-downloader?label=firefox&logo=firefox)](https://addons.mozilla.org/addon/hls-video-downloader)
[![GitHub Release Version](https://img.shields.io/github/v/release/cssnr/hls-downloader-client?logo=github)](https://github.com/cssnr/hls-downloader-client/releases/latest)
[![Build](https://github.com/cssnr/hls-downloader-client/actions/workflows/build.yaml/badge.svg)](https://github.com/cssnr/hls-downloader-client/actions/workflows/build.yaml)
[![Quality Gate Status](https://sonarcloud.io/api/project_badges/measure?project=cssnr_hls-downloader-client&metric=alert_status)](https://sonarcloud.io/summary/new_code?id=cssnr_hls-downloader-client)
# HLS Video Downloader Client

HLS Video Downloader Native Messaging Client for Windows, Linux and macOS.

- Windows: [install-win.exe](https://github.com/cssnr/hls-downloader-client/releases/latest/download/install-win.exe)
- Linux: [install-linux.deb](https://github.com/cssnr/hls-downloader-client/releases/latest/download/install-linux.deb)
- macOS: Coming Soon...

Web Extension: https://github.com/cssnr/hls-video-downloader

## Browsers

Tested and working in the following browsers:

- Firefox
- Waterfox
- Edge
- Chrome
- Chromium
- Brave
- Opera
- Vivaldi
- Ghost

## Installing

Download and run the installer for your operating system from the latest 
[release](https://github.com/cssnr/hls-downloader-client/releases/latest).

## Building

### Windows

Build the App:
```shell
python -m pip install pyinstaller
pyinstaller --noconfirm client.spec
python manifest.py
```

Create the Installer:
```shell
iscc.exe install-win.iss
```

### Linux

```shell
python manifest.py
bash install-linux.sh
```

### MacOS

> [!NOTE]  
> The macOS installer must be manually created until an automated process is added.  
> For more details on a unix install, see [install-linux.sh](install-linux.sh).

```shell
python manifest.py
```

Manifest files must be renamed to: `org.cssnr.hls.downloader.json`

Manifest key `path` must be set to the absolute path to the `client.py` location.

Manifest files must be placed in specific directories:

- Firefox: `~/Library/Application Support/Mozilla/NativeMessagingHosts`
- Chromium: `~/Library/Application Support/Chromium/NativeMessagingHosts`
- Google Chrome: `~/Library/Application Support/Google/Chrome/NativeMessagingHosts`

If the `client` location is not writable by the user, a writable `log.txt`
must be created at that location due to the current logging configuration in the [client.py](src%2Fclient.py).

The `client.py` must be executable by the user with Python installed and working.
