# Trailer Studio

A browser-based AI trailer editor prototype.

## What it does

1. Takes your Gemini API key and uploads the selected video to the Gemini Files API.
2. Uses Gemini 3.6 Flash video understanding, preferring agentic inspection when available and falling back to standard video analysis if the API rejects that mode.
3. Creates a trailer plan with factual shot descriptions and timestamps, then asks Gemini to independently verify the selected moments.
4. Lets you inspect the source video, edit shot names and timestamps, remove shots, or add a shot at the current preview position before rendering.
5. Uses FFmpeg.wasm in the browser to cut the selected clips, normalize them, add cross-fade transitions, append an optional ending image, and mix optional background music.
6. Shows the rendered MP4 in a player and provides an MP4 download. The edit plan can also be downloaded as JSON.

## Run

Enable GitHub Pages for this repository and open the published site, or serve the repository over HTTPS/local HTTP for testing. The first render downloads FFmpeg.wasm and may take a while.

## API key and privacy

Each user enters their own Gemini API key. The page keeps it in memory only; it does not save it in local storage or commit it to the repository. The key is sent to Google with API requests. A browser-based key can be inspected by the person using the browser, so this is a personal-use tool rather than a public shared-key service.

The source video is uploaded to Google's Gemini API for analysis. Do not upload private or sensitive footage.

## Current limitations

- AI video descriptions can still be wrong. Review each shot in the source preview and correct its name or timestamps before rendering.
- The optional music upload is supported; automatic composition of original music and generated sound effects is not implemented yet.
- The browser renderer applies cross-fades between clips. More transition types and per-shot effects can be added later.
- Original source audio is not currently carried through the cut sequence.
- Rendering performance depends on the device's memory and processing power. Large videos may fail in a mobile browser.
- This is a prototype. The JavaScript syntax has been checked, but a complete real-device video export test has not yet been performed.
