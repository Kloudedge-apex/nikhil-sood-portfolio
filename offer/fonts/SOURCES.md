---
title: "Self-hosted font sources and licences"
date: 2026-08-02
status: verified at source, not assumed
---

# Fonts, self-hosted

Four files, self-hosted so the offer page stops sending visitor IPs to Google two sections above the
data-handling promise. All three families carry the same licence.

| Family | Weights covered | File | Source URL |
|---|---|---|---|
| Bricolage Grotesque | 500, 700, 800 (one variable file, opsz and wght both live in it) | `bricolage-grotesque.woff2` | https://fonts.gstatic.com/s/bricolagegrotesque/v9/3y9K6as8bTXq_nANBjzKo3IeZx8z6up5BeSl9D4dj_x9PpZBMlGIInHWVyNJ.woff2 |
| Inter | 400, 500, 600 (one variable file) | `inter.woff2` | https://fonts.gstatic.com/s/inter/v20/UcC73FwrK3iLTeHuS_nVMrMxCp50SjIa1ZL7W0Q5nw.woff2 |
| Space Mono | 400 | `space-mono-400.woff2` | https://fonts.gstatic.com/s/spacemono/v17/i7dPIFZifjKcF5UAWdDRYEF8RXi4EwQ.woff2 |
| Space Mono | 700 | `space-mono-700.woff2` | https://fonts.gstatic.com/s/spacemono/v17/i7dMIFZifjKcF5UAWdDRaPpZUFWaHi6WZ3Q.woff2 |

Bricolage Grotesque and Inter are true variable fonts on Google Fonts: the same physical file covers
every weight declared for it in the page's `@font-face` block, exactly how fonts.googleapis.com itself
serves them to a modern browser (verified by fetching the css2 endpoint directly and diffing the
returned URLs byte for byte). Space Mono is a static family, so 400 and 700 are genuinely two files.
Only the latin-subset instance of each was downloaded (Unicode range U+0000 to U+00FF), which covers
every character this page uses, including the Euro sign.

Licence, verified at source rather than assumed: all three are the **SIL Open Font License, Version
1.1**, confirmed by fetching each family's `OFL.txt` from the canonical `google/fonts` repository, and
bundled in this directory rather than only linked, since the OFL expects the licence to travel with
any redistribution of the font files themselves:

- Bricolage Grotesque: `bricolage-grotesque-OFL.txt`, fetched from
  https://github.com/google/fonts/blob/main/ofl/bricolagegrotesque/OFL.txt
- Inter: `inter-OFL.txt`, fetched from https://github.com/google/fonts/blob/main/ofl/inter/OFL.txt
- Space Mono: `space-mono-OFL.txt`, fetched from
  https://github.com/google/fonts/blob/main/ofl/spacemono/OFL.txt

The OFL explicitly permits the Font Software to be bundled, embedded, redistributed and sold as part
of a larger software work, which covers self-hosting on a web page; no on-page attribution is
required. The three `.txt` files above are the actual licence text, not just a pointer to it.
