# Asteroids

A single-file HTML5 Asteroids clone — no build step, no dependencies, no external assets. Just open `index.html` in a browser.

## Play

- **Local file:** open `index.html` in any modern browser. `file://` works offline; no server needed.
- **GitHub Pages:** Settings → Pages → Deploy from a branch → root.
- **Netlify Drop:** drag `index.html` onto https://app.netlify.com/drop.

## Run a local server

Useful for testing on a phone over your LAN, or for browsers that restrict `file://`.

```sh
# Python 3 (preinstalled on macOS / most Linux)
python3 -m http.server 8000

# Node (no install — uses npx)
npx serve -l 8000

# PHP
php -S 0.0.0.0:8000
```

Then open `http://localhost:8000`. From a phone on the same Wi-Fi, use `http://<your-machine-ip>:8000` (find the IP with `ipconfig getifaddr en0` on macOS).

## Controls

**Keyboard:** ← → rotate · ↑ thrust · Space fire · M mute

**Touch:** on-screen buttons (rotate / thrust / fire), or tap canvas to fire.

## Android

The game already works in mobile browsers. To make it feel like a native app:

- **Add to Home Screen** (zero work): host the page (GitHub Pages or any HTTPS URL), open it in Chrome on Android, menu → *Add to Home screen*. Launches full-screen with its own icon.
- **Real APK from the web app**: turn the page into a PWA (manifest + service worker), then wrap it with [Bubblewrap](https://github.com/GoogleChromeLabs/bubblewrap) or [PWABuilder](https://www.pwabuilder.com/) to produce a signed `.apk` / `.aab` you can sideload or publish to Play Store.
- **WebView wrapper**: use [Capacitor](https://capacitorjs.com/) or Cordova to bundle `index.html` directly into an APK. More setup (Android Studio + JDK), but no need to host the site online.
