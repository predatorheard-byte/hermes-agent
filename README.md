# Reproduction artifacts for NousResearch/hermes-agent#105184

- `repro/repro-bundle-corrupt.js` — reconstructed corrupted renderer bundle
  (valid bundle minus the 10-byte identifier token `categories`, byte-level
  equivalent to the artifact shipped by the 2026-09-07 in-app update).
  Reproduces: `SyntaxError: Unexpected token ':'` under
  `node --input-type=module --check` and in Electron's renderer (line 440).
- `repro/repro-bundle-corrupt.js.gz` — the same, gzipped (934 KB).
- `repro/desktop-log-excerpts.log` — desktop.log excerpts from both incidents
  (2026-09-02 `index-C4jgdn_N.js:22`, 2026-09-07 `index-Ci1GuYVJ.js:440`).

Check: `node --input-type=module --check < repro/repro-bundle-corrupt.js`
