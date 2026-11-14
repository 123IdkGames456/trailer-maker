# Trailer Studio

A browser-based AI trailer planning prototype.

## Current functionality

- Accepts a Gemini API key in the browser (not saved in the repository or browser storage).
- Uploads a video to the Gemini Files API for analysis.
- Uses `gemini-3.6-flash` to suggest a trailer concept and timestamped clip sequence.
- Runs a second AI review of the proposed edit plan.
- Supports optional ending-image and music uploads in the interface.
- Exports the AI edit plan as JSON.

## Current limitation

This first version creates and reviews the edit plan only. It does **not yet render or export the edited MP4**. The next development step is a browser video renderer (for example, FFmpeg.wasm) that applies the clip cuts, transitions, ending image and music.

## Run

Serve the repository with GitHub Pages or another HTTPS static host, then open `index.html`. A local HTTP server is recommended for testing because browser modules and media APIs can behave differently when opened as a local file.

## API key and privacy

Each user must provide their own Gemini API key. The key is held in page memory and sent to Google with API requests. It is not written into source code, local storage, or this repository. Browser-based API keys are visible to the person using the browser, so this is intended as a personal-use prototype, not a public shared-key service.

Video files are uploaded to Google's Gemini API for analysis. Do not upload sensitive or private footage.
