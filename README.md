# CallPrep API Documentation

This repository contains the documentation for the CallPrep API,
built with [Mintlify](https://mintlify.com).

## Local development

Install the Mintlify CLI:

```bash
npm install -g mintlify
```

Run locally:

```bash
mintlify dev
```

Open [http://localhost:3000](http://localhost:3000).

## Structure

```
├── mint.json                    # Mintlify configuration
├── openapi.yaml                 # OpenAPI 3.1 spec (auto-generates API reference)
├── introduction/
│   ├── overview.mdx
│   ├── quickstart.mdx
│   └── how-it-works.mdx
├── authentication/
├── api-reference/               # Generated from openapi.yaml
├── guides/
├── integrations/
├── sdks/
├── plans/
├── changelog/
└── support/
```

## Deployment

Mintlify auto-deploys from the `main` branch on every push.
The docs are available at [docs.callprep.app](https://docs.callprep.app).

## Adding a new page

1. Create a `.mdx` file in the appropriate directory
2. Add the path to `mint.json` under `navigation`
3. Push to `main`

## Updating the API reference

Edit `openapi.yaml` — Mintlify will regenerate the API reference automatically.

## Writing style

- Use active voice
- Keep examples runnable (real base URL, realistic data)
- Mark future features with `<Note>Coming soon</Note>`
- Use `<Tip>` for best practices, `<Warning>` for gotchas
