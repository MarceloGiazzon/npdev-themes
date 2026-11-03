# npdev-themes

Community themes for [NPDev](https://github.com/MarceloGiazzon/NPDevGeneral): the Manager and every generated app.

A theme is one JSON file (`npdev-theme.v1`) in `themes/<id>.json`. This repository will also hold an `index.json`
(generated, with a `sha256` per theme) that the Manager's **Browse themes** reads over HTTPS; the Manager verifies
the hash before it imports anything.

Status: just created. The catalogue format, the checker and the contribution flow are being added.
