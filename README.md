# Smart Checkpoints Documentation

Source for [docs.smartcheckpoints.xyz](https://docs.smartcheckpoints.xyz), built
on [Mintlify](https://mintlify.com).

## Layout

```
index.mdx            Introduction
quickstart.mdx       Server to first violation
concepts/            The graph model, enforcement, distance drivers, data quality
reference/           REST API, realtime events, driver protocol, the map bridge,
                     the console, data model
docs.json            Navigation, theme, fonts, footer
style.css            Mono font, applied on top of the docs.json theme
logo/                Lockups for the light and dark navbar
```

## Local preview

```bash
npm i -g mint
mint dev
```

Run it from this directory, where `docs.json` lives. The preview is on
`http://localhost:3000`.

## Publishing

Changes deploy automatically when they land on the default branch, through the
Mintlify GitHub app.

## Keeping it true

Every protocol and schema detail here is documented against the code in
[`server`](https://github.com/smart-checkpoints/server) and
[`driver-osrm`](https://github.com/smart-checkpoints/driver-osrm), not against a
spec. The driver protocol is v2; the REST, realtime, and storage references
track `server.js`, `database.js`, `api-key-manager.js`, and `diagnostics.js`.
When any of them changes, the reference pages change with it.
