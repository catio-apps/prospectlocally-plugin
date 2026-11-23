---
name: get-started
description: Walk a new ProspectLocally user through connecting their account, checking their credit balance, and running a first Google Maps business search.
---

# Get started with ProspectLocally

ProspectLocally searches Google Maps for a business niche in one or more locations. Each result is a Google Maps listing with the business name, category, address, phone number, website address, rating, and review count. The user's account connects the first time a tool needs it: Claude Code opens a sign-in page in the browser, and the user signs in there.

Help the user run a first search.

1. Call `check_credits` and tell the user how many credits the account has left.
2. Ask which business niche and which place they want, such as "plumber" in "Whitehorse, Yukon".
3. Call `find_location` with the place, and confirm the match with the user.
4. Before calling `search_businesses`, state the most credits it can cost (the depth, 300 by default) and wait for the user to say yes.
5. Call `search_status` until the search finishes, then call `get_results` and show the businesses with their name, category, address, rating, and website address.
6. To review the account's campaigns, call `list_campaigns`.

## Rules

- Never run a paid tool without the user's yes, and never repeat a paid call the user did not ask for.
- The tools return only the Google Maps listing. They do not provide owner names or email addresses, and they do not send messages to the businesses.
- Do not offer plans, prices, or credit purchases.
- Never ask the user for a password or a one-time code. The sign-in page handles authentication.
