McBot update notes

Changed files: index.js, settings.json. Other runtime files are included unchanged for convenience.

Railway variables (Project -> Service -> Variables):
- OPENAI_API_KEY = your secret OpenAI API key (do NOT put the key in GitHub source)
- OPENAI_MODEL = gpt-4o-mini (optional)
- DASHBOARD_TOKEN = a long random secret (required for dashboard username changes)

The AI API integration code is in index.js and reads OPENAI_API_KEY from Railway at runtime.
Never commit the actual API key to GitHub. ChatGPT subscription is separate from API billing.

In-game chat rules: only messages beginning with a dot are processed. Plain chat is ignored and never sent to AI.
Owner username configured as wingxmc4893. Add admin usernames in settings.json -> owner.admins.

Offline-mode username change: .name <username> or Dashboard username form. Requires DASHBOARD_TOKEN for dashboard. This changes the configured offline bot username and reconnects; it cannot rename a Microsoft account. Railway filesystem may be ephemeral, so settings.json changes made at runtime can be lost on redeploy.

PvP: .pvp starts a duel only against the command sender; .pvpstop ends it. Bot death ends duel. Opponent death is detected when Mineflayer emits entityDead for the tracked entity. Real server behavior can vary by server/plugins; test on a private test server first.

Inventory: Dashboard shows live inventory slots, held items, armor/equipment, health and food via /api/inventory.
