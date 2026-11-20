# Bludia documentation

Source for the Bludia docs site, built with [Mintlify](https://mintlify.com).

## Local preview

```bash
npm i -g mint
mint dev            # http://localhost:3000
mint broken-links   # check internal links
```

Run commands from this folder (where `docs.json` lives).

## Editing

- Pages are `.mdx` files; navigation is in `docs.json`.
- The API Reference tab is generated from `api-reference/openapi.json`.
- See `AGENTS.md` for structure, terminology, and style rules.

## Publishing

Changes pushed to the default branch deploy automatically through the Mintlify GitHub app.

## AI and LLM access

Mintlify serves `/llms.txt` and `/llms-full.txt` automatically, and every page can be copied as Markdown or opened in ChatGPT, Claude, Perplexity, Cursor, or VS Code from the page menu. `reference/at-a-glance.mdx` is a single-page fact sheet for quick answers.
