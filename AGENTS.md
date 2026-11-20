# Bludia documentation: instructions for AI agents

For Mintlify product knowledge (components, configuration, writing standards), install the Mintlify skill: `npx skills add https://mintlify.com/docs`

## About this project

- Documentation site for **Bludia**, a backend platform (beta), built on [Mintlify](https://mintlify.com).
- Pages are MDX files with YAML frontmatter. Navigation lives in `docs.json`.
- The API Reference tab is generated from `api-reference/openapi.json`. Keep it in sync with `backend/routes/api/v1.php`.
- Source of truth for behavior is the backend code (`backend/app`). When docs and code disagree, verify in code.

## Structure

| Folder | Content |
| :-- | :-- |
| root | `introduction`, `quickstart`, `concepts`, `projects` |
| `database/` | Collections, fields, validation, records, relations, computed fields, import/export |
| `api/` | Public REST API: auth, keys, querying, errors, rate limits, CORS |
| `authentication/` | Guards and end-user auth flows |
| `authorization/` | Roles, permissions, row-level security, team members |
| `hooks/` | Go/WASM hooks and SDK |
| `messaging/`, `files/`, `reports/`, `automation/` | Other features |
| `frontend/`, `hosting/`, `guides/` | Integration and how-tos |
| `api-reference/` | OpenAPI-driven reference |
| `reference/`, `troubleshooting/` | Fact sheet, limits, glossary, FAQ, errors |

## Terminology

- **end user**: a person using the customer's app (record in a collection, signs in via a guard). Never "customer" or "member" in a generic sense.
- **team member**: a person managing the project in the Bludia dashboard.
- **collection** (not table), **record** (not row), **field** (not column), **guard** / **authentication guard**, **row policy** / **row-level security**, **hook** (not webhook or trigger).
- **API key** types: `platform` and `end_users` (code formatting, exact spelling).
- Header: `X-BLUDIA-API-KEY`. Base URL placeholder: `https://YOUR_API_HOST/ext/api/v1`, `$BASE_URL` in shell examples.
- Hook events in camelCase (`beforeInsert`); `ctx.Operation()` values in snake_case (`before_insert`).

## Style

- Active voice, second person, sentence-case headings, one idea per sentence.
- Bold for UI elements (**Settings**), code formatting for paths, fields, headers, values.
- Every page needs `title`, `description` (one factual sentence with concrete details), `keywords`, and `icon` (lucide).
- Lead with a one-paragraph summary, then tables of facts. Prefer exact values (defaults, limits, status codes) over vague wording, so pages answer questions on their own when read by LLMs.
- Use Cards/CardGroups for navigation, Steps for procedures, Tabs/CodeGroups for alternatives, Accordions for FAQs, and Note/Tip/Warning/Danger callouts sparingly.
- Section colors for card icons: database `#3B82F6`, API `#0EA5E9`, auth `#8B5CF6`, authorization `#10B981`, hooks `#F59E0B`, messaging `#EC4899`, files `#6366F1`, reports `#14B8A6`, automation `#F97316`.

## Content boundaries

- Document only the public API (`/ext/api/v1`) and dashboard features. Don't document internal routes (`/api/internal/ipc`, guest/AI internals, platform admin).
- Mark unfinished features honestly as beta or "coming soon"; don't describe them as available.
- Never include real keys, emails, or customer data in examples.
