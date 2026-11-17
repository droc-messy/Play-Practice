# 🎭 Play Practice

A single-page web app for rehearsing a play script. Paste your script, pick the character (or characters) you are playing, and the app reads every other role aloud with text-to-speech and waits for you on your lines.

No build step, no dependencies: open `index.html` in a browser, or host it on any static host (GitHub Pages, Netlify, Cloudflare Pages).

## Features

- **Script format:** one line per speech, written as `CHARACTER: what they say`.
  - Stage directions in `(parentheses)` or `[brackets]` are shown but not spoken.
  - `ALL: ...` lines are said by everyone together.
- **Up to 4 players** on one device. The roles nobody picked are spoken automatically.
- **Listening:** the app listens through the microphone and highlights your words as you say them, then moves on when you finish. A manual **I said it** button (or the space bar) always works.
- **Hide my words:** each player can hide their own lines to rehearse from memory. **💡 Show this phrase** reveals one line if you get stuck.
- **Hide the words for all other roles:** hides everyone who is not a player.
- **Shared cues:** directions aimed at the whole cast, such as `(Everyone laughs.)` or `ALL: (laugh)`, light up the whole stage, stay on screen longer, and the automatic roles laugh along.
- **Three speeds:** Slow, Medium and Fast. Faster speeds also shorten the pauses between speakers.
- **Voices:** each character gets a distinct voice from the voices installed in the browser, and you can change any of them under **📜 Script & voices**.
- **Curtain call:** at the end it shows how many lines you said and how many you managed without help.

## Using it

1. Open the app and, if you like, paste your own script under **📜 Script & voices**, then press **Load**. A sample script is included.
2. Choose who is playing (up to four players).
3. Optionally tick **Hide my words** and/or **Hide the words for all other roles**, and pick a speed.
4. Press **Start**.

Your script is saved in the browser (`localStorage`) so it is still there next time.

## Browser notes

- **Best experience:** Chrome or Edge. They support both speech output and microphone word recognition.
- **Edge** has free, human-sounding "Natural" voices. If no sound plays, the app falls back to a local voice.
- **Safari and Firefox:** speech output works, but word recognition is limited or missing. Use the **I said it** button or the space bar to move on.
- Microphone access requires HTTPS (or `localhost`).
- Voices differ between devices, so the sound will vary. For nicer voices on a phone, install the enhanced voices in the device's speech settings.

## Hosting

Because it is one static file, any static host works. For GitHub Pages: repository **Settings → Pages**, deploy from the `main` branch and root folder.
