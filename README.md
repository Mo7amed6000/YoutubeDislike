# YoutubeDislike (Safari)

A **Safari Web Extension for macOS** that restores **YouTube dislike counts** on watch pages. The extension injects the [Return YouTube Dislike](https://returnyoutubedislike.com/) content logic and fetches public vote estimates from the [Return YouTube Dislike API](https://returnyoutubedislikeapi.com/).

## Features

- Shows estimated dislike counts next to likes on `youtube.com` watch URLs
- Toolbar popup to confirm the extension is active
- Works with Safari’s Web Extension model (Manifest V2)

## Requirements

- macOS with **Safari** (Safari 14+ recommended for Web Extensions)
- **Xcode** to build and run the host app (open `YoutubeDislike.xcodeproj`)

## Build and install (development)

1. Clone this repository.
2. Open `YoutubeDislike.xcodeproj` in Xcode.
3. Select the **YoutubeDislike** scheme and your Mac as the run destination.
4. Build and run (**⌘R**). Xcode installs the containing app and registers the extension.
5. In **Safari → Settings → Extensions**, enable **YoutubeDislike Extension** and allow it on YouTube if prompted.

After code changes to the extension resources, rebuild from Xcode and reload the extension in Safari (or disable/enable it in Settings).

## Project structure

| Path | Purpose |
|------|---------|
| `YoutubeDislike/` | macOS host app (enables and manages the Safari extension) |
| `YoutubeDislike Extension/` | Safari Web Extension (manifest, content script, popup) |
| `YoutubeDislike Extension/Resources/content.js` | Return YouTube Dislike–based logic for YouTube pages |
| `Icons/` | Branding and store/marketing assets |

## Configuration

Behavior options for the content script live at the top of `YoutubeDislike Extension/Resources/content.js` in the `extConfig` object (logging, bar colors, number format, etc.). See comments in that file for allowed values.

## Privacy and third-party services

- The extension runs only on `https://www.youtube.com/*` (see `manifest.json`).
- Dislike/like estimates are requested from **returnyoutubedislikeapi.com** when you view a video. Review [Return YouTube Dislike](https://returnyoutubedislike.com/) for their privacy policy and data practices.
- This project is **not** affiliated with Google or the official Return YouTube Dislike team unless stated otherwise; it is a Safari port/wrapper using their open userscript approach.

## Credits

- Dislike restoration logic and API integration are based on **[Return YouTube Dislike](https://github.com/Anarios/return-youtube-dislike)** (Anarios & JRWR) and [returnyoutubedislike.com](https://returnyoutubedislike.com/).

## License

This project is licensed under the MIT License.
You are free to use, modify, and distribute this project, provided that the original copyright notice and license are retained.
