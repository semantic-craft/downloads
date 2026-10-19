# downloads

Public downloads for Anamra, Owltype and Glaux, served at `https://downloads.responsay.com`.

- `site/` is deployed by Cloudflare Pages on every push to `main`: update feeds (Sparkle `appcast.xml`,
  `latest.json`), release notes, checksums, SBOMs and provenance files.
- Installers and archives (`.dmg`, `.pkg`, `.tar.gz`) are GitHub Release assets of this repository,
  one release per product version (`anamra-1.3.0`, `owltype-2.0.14`, `glaux-v2.5.2`, ...).
  `site/_redirects` sends each historical URL to its asset, so installed apps keep working.
- Releases are published by each product's release script, which uploads the assets first and
  pushes the feed change last.

`MIRROR.sha256` records the SHA-256 of every object copied from the previous storage on 2026-10-19.
Source code for these apps is not in this repository.
