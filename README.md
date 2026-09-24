## macmillernz Umbrel Community App Store

Chromium and Firefox for umbrelOS, using the [linuxserver.io](https://linuxserver.io) images.

Umbrel removed its official versions because the current linuxserver.io images need HTTPS, and Umbrel's app proxy only serves plain HTTP. These apps work around that:

| App      | Dashboard tile (redirects) | Browser (HTTPS, self-signed) |
|----------|----------------------------|------------------------------|
| Chromium | `http://umbrel.local:3480` | `https://umbrel.local:3481`  |
| Firefox  | `http://umbrel.local:3490` | `https://umbrel.local:3491`  |

- The dashboard tile goes through Umbrel's login, then redirects to the HTTPS port.
- The HTTPS port uses the image's self-signed certificate, so your browser will show a warning the first time. Accept it to continue.
- The HTTPS port bypasses Umbrel's login, so it has its own basic auth. The username is `umbrel`, and umbrelOS shows the password when you open the app.
- Browser profiles are kept in the app's data directory and survive restarts and updates.

### Install

In umbrelOS, go to **App Store → ⋯ → Community App Stores**, paste `https://github.com/macmillernz/umbrel-community-app-store`, and add it.

### Updating

Images are pinned by tag and digest. To update one, change the `image:` line in `docker-compose.yml` and bump `version` in `umbrel-app.yml`.
