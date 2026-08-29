# Documentation project instructions

## About this project

- The documentation site for Smart Checkpoints, built on [Mintlify](https://mintlify.com)
- Pages are MDX files with YAML frontmatter, configuration lives in `docs.json`
- The theme mirrors the marketing site: Space Grotesk for headings, Inter for
  body, JetBrains Mono for code, primary `#19c4d8`
- Source of truth for anything technical is the code in the `server` and
  `driver-osrm` repositories, never a spec. Read the code before documenting a
  protocol detail

## Terminology

- A **checkpoint** is the physical camera. A **node** is its record in the graph
- An **edge** is an enforced stretch of road, stored in the `connections` table.
  Prefer "edge" in prose and `connection` only when naming the database or API field
- A **distance driver** is the external process that answers road distances. A
  **map driver** is the external process that serves the console's map view.
  Never shorten either to "driver" alone on first use in a page
- A **project** is one deployment. Its own key is an **operator key** (full read
  and write); a **reporter key** is issued per camera and can only report a
  sighting
- An edge carries a **`distance_status`** of `ok`, `unknown`, or `no-route`.
  Only `ok` enforces; `distance` is NULL otherwise. There is no placeholder zero
- Distances are always metres, speed limits always km/h, coordinates always WGS84

## Style preferences

- Use active voice and second person ("you")
- Keep sentences concise, one idea per sentence
- Use sentence case for headings
- Bold for UI elements: Click **Settings**
- Code formatting for file names, commands, paths, and code references
- No em dashes anywhere

## Content boundaries

- Document the behaviour that exists, including the sharp edges. An edge that
  silently stops enforcing because its distance is `unknown` is documentation,
  not a bug report
- Do not document the admin pages beyond the fact that they exist and how they
  authenticate
- Do not invent endpoints, fields, or environment variables. If it is not in the
  code, it does not go in the docs
