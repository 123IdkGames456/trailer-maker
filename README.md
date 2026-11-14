# Trailer Studio

A browser-based AI trailer editor prototype.

## What it does

1. Takes a Gemini API key and uploads a selected video to the Gemini Files API.
2. Uses `gemini-3.6-flash` to analyze the video and propose a trailer sequence with timestamps.
3. Asks Gemini to review the edit plan and, when needed, return a revised clip sequence.
4. Uses FFmpeg.wasm in the browser to cut the selected clips, add short cross-fade transitions, append an optional ending image, and mix an optional music track.
5. Exports an MP4 for preview and download.
6. Can also export the AI edit plan as JSON.

## Run

Enable GitHub Pages for this repository and open the published site, or serve the repository over HTTPS/local HTTP for testing. The first render downloads FFmpeg.wasm and may take a while.

## API key and privacy

Each user enters their own Gemini API key. The page keeps it in memory only; it does not save it in local storage or commit it to the repository. The key is sent to Google with API requests. A browser-based key can be inspected by the person using the browser, so this is a personal-use tool rather than a public shared-key service.

The source video is uploaded to Google's Gemini API for analysis. Do not upload private or sensitive footage.

## Current limitations

- The optional music upload is supported; automatic composition of original music and generated sound effects is not implemented yet.
- The browser renderer applies a cross-fade between clips. More transition types and per-shot effects can be added later.
- Original source audio is not currently carried through the cut sequence.
- Rendering performance depends on the device's memory and processing power. Large videos may fail in a mobile browser.
