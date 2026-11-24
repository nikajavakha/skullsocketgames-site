# skullsocketgames.com

The studio's site, [skullsocketgames.com](https://skullsocketgames.com), hosted on GitHub Pages: GitHub's Jekyll builds
`main`. `_config.yml` publishes `.well-known/` (Jekyll skips dot folders otherwise) and leaves this README out.

| Path | What it is for |
|---|---|
| `/` (`index.html`) | Forwards to [Impostor Online on Steam](https://store.steampowered.com/app/2966570/Impostor_Online/). |
| `/join/?c=CODE` | The fallback behind the game's invite links. Shows the table code and one store button picked from the browser (Google Play on Android, Steam on a desktop, none elsewhere). On Android with the game installed, the game opens instead. Not indexed. |
| `/.well-known/assetlinks.json` | Android App Links: lets the Android game (`com.skullsocket.impostoronline`) open `/join/` links itself. |
| `/privacy/` | Privacy policy. |
| `/terms/` | Terms of service, with the community rules. |
| `/delete-account/` | How to delete an account, and what is deleted and kept (Google Play requires this page). |
| `/support/` | How to reach the studio and how to report a player. |

`assets/site.css` styles every page. Nothing loads from another host.

## The policy pages link to no store

The game opens `/privacy/`, `/terms/`, `/delete-account/` and `/support/` in the player's browser, phones included. So
these four pages link to no store: no link or button to Steam, Google Play or the App Store, and no link to `/` (it
forwards to Steam) or to `/join/` (it has store buttons). A page a phone app opens must not lead to another way to pay
(Google Play's payments policy), and the Steam build may not link to a store without Steam Wallet (Valve). Naming
Steam or Google Play in text is fine, and so are links between the four pages and `mailto:` links.

This must print nothing:

    grep -nE 'steampowered|play\.google|apps\.apple|href="/"|href="/join|href="https://skullsocketgames.com/?"' privacy/index.html terms/index.html delete-account/index.html support/index.html
