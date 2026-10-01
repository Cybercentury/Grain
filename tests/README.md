# Browser regression audit

Run from the repository root with Node.js 20+:

```sh
npm install --no-save playwright
npx playwright install chromium
node tests/audit.mjs
```

Optional `CHROMIUM_EXECUTABLE_PATH` points to an existing compatible Chromium.
`AUDIT_ARTIFACT_DIR` overrides the `.audit-artifacts` output directory.
The script starts its own localhost server on port 8765, injects test-only access into the served module, tests read and write scenarios in memory, and closes the browser/server. It does not modify data.json or transmit CRM data externally. The server port must be free.
