OpenAI API key placement (GitHub file method)

1. Open index.js.
2. Near the top, find:
   const OPENAI_API_KEY = "PASTE_OPENAI_API_KEY_HERE";
3. Replace PASTE_OPENAI_API_KEY_HERE with your actual OpenAI secret key, keeping the quotes.
4. Commit the changed index.js to your GitHub repository. Railway should redeploy from the repository if auto-deploy is enabled.

Security warning: storing a real API key in a GitHub file is risky. Anyone with repository access can read it, and a public repository exposes it publicly. The safer option is Railway Variables with OPENAI_API_KEY. Never share the key in chat or screenshots. If the key is exposed, revoke it and create a new one.
