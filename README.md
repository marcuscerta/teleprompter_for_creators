# Teleprompters for Creators

A simple, reliable teleprompter for the iPad. It is one static web page: no accounts, no subscription, no App Store. Once it has loaded it works offline, and your script never leaves the device.

**Live site:** https://marcuscerta.github.io/teleprompter_for_creators/

## Features

**Reading**
- Paste a script or import a `.txt` file. One script at a time, saved on the device.
- Smooth auto-scroll with adjustable speed, font size, text width and line spacing.
- Reading-line guide, a countdown before it starts, and a "time left" estimate.
- Three themes: white on black, yellow on black, black on white.
- Tap the text to play or pause, drag to scrub, and use the on-screen buttons to jump back or forward a few lines.

**Teleprompter hardware (e.g. Neewer X11)**
- **Mirror** and **Flip** the text for beam-splitter glass. Both can be toggled live.
- Controls fade out a few seconds after you press play, so AirPlay or HDMI output shows only the text. A **Blank screen** button blacks everything out.

**Bluetooth remote (e.g. Satechi R2)**
- The remote sends ordinary keyboard keys. Use **Learn** in settings, press the button you want, and it is mapped to that action.
- Default keys:

  | Action | Default keys |
  |---|---|
  | Play / pause | PageDown, →, Space, Enter |
  | Back a few lines | PageUp, ← |
  | Faster / slower | ↑ / ↓ |
  | Forward a few lines | F |
  | Back to top | Home |
  | Record start / stop | R |
  | Blank screen | `.` or B |
  | Show / hide controls | C |
  | Exit to script | Esc |

**Camera and recording**
- Turn on **Camera behind text** to see yourself while you read. Front camera by default, back camera selectable, with adjustable brightness behind the text.
- **Record** saves the camera and microphone. It can also start the scroll for you, and `R` on your remote starts and stops it.
- Quality choices are 1080p (default, usually the widest view), 720p and 4K. Some webcams crop in when asked for 4K, so check the picture first. The resolution the camera is actually using is shown in the controls bar, and a camera picker appears when more than one camera is available.
- When you stop, choose **Save to Photos / Share…** (pick **Save Video** in the share sheet) or **Download file**. The video stays in memory until you save it or dismiss the screen.
- The preview is mirrored like a selfie, but the saved video is not. The recording does not include the script text.

## Install on the iPad

1. Open the live site above in **Safari**.
2. Tap Share, then **Add to Home Screen**.
3. Open it from the Home Screen icon. It runs full screen and works offline.

If you installed an older version, close the app and reopen it (or delete and re-add it) to pick up updates.

## Tips

- **Screen mirroring to an Apple TV or monitor:** the TV shows whatever is on the iPad, so let the controls auto-hide, or use the remote.
- **Camera permission:** Safari asks the first time. If it was blocked, allow it under Settings → Safari → Camera and Microphone.
- **Interruptions:** if you switch apps or lock the iPad mid-recording, iPadOS can stop the camera. Whatever was recorded up to that point goes to the save screen.
- **Quality:** recording in a web app is below the built-in Camera app (no 4K guarantee, no lens or exposure controls). If it is not good enough, record with a dedicated camera app and use this only as the teleprompter.

## Project layout

| File | Purpose |
|---|---|
| `index.html` | The whole app (HTML, CSS and JavaScript) |
| `manifest.webmanifest`, `icon*.png/svg` | Home Screen install details |
| `sw.js` | Service worker that makes it work offline |
| `.github/workflows/pages.yml` | Deploys the site to GitHub Pages on every push to `main` |

There is no build step. To try it locally, serve the folder over HTTP (for example `python3 -m http.server`) and open it in a browser. The camera needs HTTPS or `localhost`.

## Deploying

In the repo, set **Settings → Pages → Source** to **GitHub Actions**. Every push to `main` then redeploys the site. You can also run the "Deploy Teleprompters for Creators to GitHub Pages" workflow by hand from the Actions tab.

## Ideas for later

- Voice-following scroll (the text keeps pace with what you say)
- A library of saved scripts
