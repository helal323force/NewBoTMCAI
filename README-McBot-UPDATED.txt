McBot updated files
===================

Replace these files in your existing GitHub repository:
- index.js
- settings.json
- .github/workflows/deno.yml

Keep the other existing files (package.json, package-lock.json, logger.js,
leaveRejoin.js, launcher_accounts.json, etc.) unchanged.

IMPORTANT SETTINGS
- owner.username is set to wingxmc4893.
- Change owner.dashboardToken from CHANGE_THIS_TO_A_LONG_RANDOM_SECRET to a long random secret before using the dashboard username-change feature.
- Add the AI provider key through GitHub repository Secrets / runtime environment variable OPENAI_API_KEY when your runtime supports it. Do not commit a real API key to a public repository.
- The settings.json server/account fields are carried forward from the supplied project; verify them before running.

Features present in this update include dot-prefixed chat commands, .ai, basic/admin/owner command checks,
username change for offline-mode bots, PvP duel targeting the command issuer with safety stop conditions,
live event feed endpoint (/events), health endpoint (/health), and inventory data endpoint (/api/inventory).

GitHub Actions workflow checks dependencies, JavaScript syntax and settings JSON. It does NOT keep the bot online:
a GitHub Actions runner ends when the job completes, so use your intended hosting runtime to run `npm start`.

Before replacing files, keep a backup of the current working files.
