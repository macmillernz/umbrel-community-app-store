## macmillernz Umbrel Community App Store

Chromium and Firefox for umbrelOS, using the [linuxserver.io](https://linuxserver.io) images.

**Requires umbrelOS 2.0 or later.** The current linuxserver.io images only work over HTTPS. umbrelOS 2.0 can serve apps over HTTPS on their normal port, and these apps set `requiresHttps: true` so the dashboard opens them that way.

| App      | Opens at                    |
|----------|-----------------------------|
| Chromium | `https://umbrel.local:3480` |
| Firefox  | `https://umbrel.local:3490` |

- Both apps are behind the normal Umbrel login. There's no separate app password.
- Your browser may show a certificate warning the first time. Accept it to continue.
- Browser profiles are kept in the app's data directory and survive restarts and updates.

### Install

In umbrelOS, go to **App Store → ⋯ → Community App Stores**, paste `https://github.com/macmillernz/umbrel-community-app-store`, and add it.

### Updating

Images are pinned by tag and digest. To update one, change the `image:` line in `docker-compose.yml` and bump `version` in `umbrel-app.yml`.
