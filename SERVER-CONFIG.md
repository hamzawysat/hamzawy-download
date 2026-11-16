# Central server configuration

The public configuration document is `server-config.json` at the root of this GitHub Pages repository.

The React Native customer/technician APK fetches this file at startup/first API use. Keep this URL stable; change the backend host and port in the JSON rather than in the APK.

Example:

```json
{
  "schemaVersion": 1,
  "configVersion": 1,
  "apiProtocol": "https",
  "apiHost": "www.hamzawy-sat.dynv6.net",
  "apiPort": 443,
  "apiPath": "/api",
  "mediaPath": "/api/media"
}
```

- Change `apiHost` and `apiPort` when the backend moves.
- Change `apiPath` only if the API prefix changes.
- `mediaPath` is served by the backend and points to MongoDB GridFS media at `/api/store/media`.
- Increment `configVersion` for every published change.
- This file is public: never put secrets or MongoDB credentials in it.

GitHub Pages deploys from `main`. A feature branch is not public until it is reviewed and merged, and the Pages workflow completes.
