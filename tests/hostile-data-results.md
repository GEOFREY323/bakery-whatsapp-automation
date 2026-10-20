# Hostile-Data Test Results

| # | Test | Input | Result | Verdict |
|---|------|-------|--------|---------|
| 1 | Normal order | Bonjour, je veux 2 baguettes... | Commandes | ✅ Pass |
| 2 | Pidgin | Abeg give me 2 bread | Commandes | ✅ Pass |
| 3 | Emojis | 2 🍞 and 1 🎂 | Commandes | ✅ Pass |
| 4 | Unclear | le truc d'hier | Review | ✅ Pass |
| 5 | Empty | (space) | Review | ✅ Pass |
| 6 | Non-order | Bonjour ça va? | Review | ✅ Pass |
| 7 | 47 items | Long order | Parsed | ✅ Pass |
| 8 | Duplicate | Same message_id twice | Blocked by dedup | ✅ Pass |
| 9 | Mixed language | Je veux 2 baguettes abeg | Commandes | ✅ Pass |

## Notes

- Test 4 originally went to "ignore" — fixed by routing non-order messages to Review
- Tests 5 and 6 now go to Review instead of being silently dropped