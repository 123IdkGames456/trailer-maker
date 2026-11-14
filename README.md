# Trailer Studio — AI Clip Finder

A browser-based AI video clip finder. It helps you find usable moments in a source video based on the mood and type of scene you want.

## Workflow

1. Enter your own Gemini API key and upload a video.
2. Gemini analyzes the footage and creates a scene inventory with timestamps and neutral visual descriptions.
3. Choose from 10 main vibe categories:
   - Horror & Suspense
   - Serious Drama
   - Love & Romance
   - History
   - Action
   - Mystery
   - Comedy
   - Adventure
   - Fantasy & Sci-Fi
   - Emotional & Inspiring
4. Each category contains 10 more specific sub-options. Select them yourself, use AI Choose for a category, or let AI choose the main categories and matching sub-options based on the footage.
5. Ask AI to find clips that match the selected vibes.
6. Preview each suggestion, select the clips you want, and download the selected moments as separate MP4 files inside one ZIP archive.

## Run

Enable GitHub Pages for this repository and open the published site, or serve the repository over HTTPS/local HTTP for testing. The first clip export downloads FFmpeg.wasm and may take a while. ZIP packaging also loads JSZip from a CDN.

## API key and privacy

Each user enters their own Gemini API key. The page keeps it in memory only; it does not save it in local storage or commit it to the repository. The key is sent to Google with API requests. A browser-based key can be inspected by the person using the browser, so this is a personal-use tool rather than a public shared-key service.

The source video is uploaded to Google's Gemini API for analysis. Do not upload private or sensitive footage.

## Current limitations

- AI can still misunderstand a scene or choose an imperfect timestamp. Preview every suggested clip before using it.
- The scene inventory and clip search depend on the video understanding and timestamp accuracy provided by Gemini.
- Exporting many long clips can use substantial memory and may fail on phones or tablets.
- Clip export keeps the source audio when present, but source formats may vary.
- The project is a prototype. JavaScript syntax has been checked, but a complete real-device video analysis and ZIP export test has not yet been performed.
