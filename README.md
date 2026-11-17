# 🎭 Play Practice

A single-page web app for rehearsing a play script. Paste your script, pick the character (or characters) you are playing, and the app reads every other role aloud with text-to-speech and waits for you on your lines.

No build step, no dependencies: open `index.html` in a browser, or host it on any static host (GitHub Pages, Netlify, Cloudflare Pages).

## Features

- **Script format:** one line per speech, written as `CHARACTER: what they say`.
  - Stage directions in `(parentheses)` or `[brackets]` are shown but not spoken.
  - `ALL: ...` lines are said by everyone together.
- **Up to 4 players** on one device. The roles nobody picked are spoken automatically.
- **Listening:** the app listens through the microphone and moves on when you finish. Over HTTPS or `localhost`, supported browsers also highlight your words as you say them. When opening `index.html` directly, it uses speech and silence detection without word-by-word highlighting to avoid repeated speech-recognition permission prompts. A manual **I said it** button (or the space bar) always works.
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
- The microphone stream and speech recognizer are reused between lines during a rehearsal, so each character's turn does not start a fresh microphone request. Recognition results are only used during a player's turn. Untick **Listen to me** to stop speech recognition; leaving the page releases the microphone.
- When opening `index.html` directly (`file://`), the app requests one microphone stream and reuses it for speech and silence detection throughout the page session. It does not start the browser's speech recognition service, which can repeatedly ask for permission on local files. Word-by-word highlighting is unavailable in this mode.
- For word-by-word recognition and reliable site permission storage, use HTTPS (such as GitHub Pages) or `localhost` and allow microphone access for that site. The app cannot override browser permission settings; reloading the page may ask for permission again.
- Voices differ between devices, so the sound will vary. For nicer voices on a phone, install the enhanced voices in the device's speech settings.

## Hosting

Public app: [Play Practice](https://droc-messy.github.io/play-practice/).

Because it is one static file, any static host works. For GitHub Pages: repository **Settings → Pages**, deploy from the `main` branch and root folder.
