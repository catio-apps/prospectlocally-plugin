# ProspectLocally plugin for Claude Code

This plugin lets Claude Code search Google Maps for a business niche in one or more locations, using your own ProspectLocally account. Each result is a Google Maps listing with the business name, category, address, phone number, website address, rating, and review count.

## Install

Run these commands in Claude Code:

```
/plugin marketplace add catio-apps/prospectlocally-plugin
/plugin install prospectlocally@prospectlocally-plugin
```

From a shell, the equivalent is `claude plugin marketplace add catio-apps/prospectlocally-plugin` followed by `claude plugin install prospectlocally@prospectlocally-plugin`.

## Sign in

The plugin connects to the remote MCP server at `https://app.prospectlocally.com/api/mcp` and uses OAuth. The first time a tool needs your account, run `/mcp`, select the `prospectlocally` server, and complete the sign-in in your browser. Sign in to your ProspectLocally account and approve access. You never type a password or a code into Claude Code.

Using an API key is optional. If you prefer one, create it in your account and add the server yourself with a bearer header, for example `claude mcp add --transport http prospectlocally https://app.prospectlocally.com/api/mcp --header "Authorization: Bearer YOUR_API_KEY"`. Do not commit a key to a repository.

## What the plugin contains

- `.mcp.json`: the remote MCP server definition.
- `skills/get-started/SKILL.md`: a skill that tells Claude when and how to use the tools.

The plugin runs no local code and no hooks. It sends requests only to `https://app.prospectlocally.com/api/mcp`, on behalf of the account you sign in with.

## What you can ask for

- Check your credit balance.
- Find a location code for a place.
- Search for a niche in that place and read the results.
- List your campaigns.

A search spends credits that your account already holds. Claude states the most it can cost and asks for your approval first. The plugin returns only the Google Maps listing. It does not provide owner names or email addresses, and it does not send messages to the businesses it finds.

## Privacy, terms, and support

- Privacy policy: https://prospectlocally.com/privacy
- Terms of service: https://prospectlocally.com/terms
- Support: https://prospectlocally.com/support
- Website: https://prospectlocally.com

## License

MIT. See [LICENSE](./LICENSE). Copyright 2026 EDSDEV INC.
