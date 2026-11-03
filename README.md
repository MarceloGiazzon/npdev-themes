# npdev-themes

Community themes for [NPDev](https://github.com/MarceloGiazzon/NPDevGeneral): the Manager and every generated app.

A theme is one JSON file (`npdev-theme.v1`) in `themes/<id>.json`: 13 hex colours, two font lists, a radius and an
elevation. It is data, never CSS, and it has to meet the WCAG contrast floors, so a catalogue theme cannot make
NPDev unreadable.

`index.json` is **generated** (never edit it by hand). The Manager's **Browse themes** reads it over HTTPS, downloads
`themes/<id>.json`, and checks the file's `sha256` against the index **before** it imports anything; a file that does
not match is refused.

## Add a theme

1. In the Manager, open **Settings → Appearance**, make your theme, and choose **Share this theme**. It opens GitHub's
   "new file" page with your JSON filled in. (Or write `themes/<id>.json` yourself.)
2. A catalogue theme must be self-contained (no `basedOn`), and carry `version`, `author` and `license`.
   The id must not be one of NPDev's own (`npdev-dark`, `npdev-light`, `retro`, `synth`, `farm`, `warm`, `windows`,
   `high-contrast`, `npdev-default`, `system`).
3. Regenerate the index: `python <NPDevGeneral>/scripts/quality/check-themes.py --catalogue . --write-index`.

CI runs that same checker (`scripts/quality/check-themes.py --catalogue`) from the NPDev repository, so a theme is
judged by exactly the rules the Manager enforces.

## Licence

Everything in this repository is open source and free to use, under the [MIT licence](LICENSE).
The four seasonal themes here are NPDev's own. By submitting a theme you agree it is published under MIT too, so its
`license` field should say `MIT` (or another free, open-source licence).
