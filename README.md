# Adblock List assembler
Inside this repo, GitHub Actions take a simple list.md file and convert it into three fully compatible filter lists.
You maintain one readable Markdown file ([list](list.md)) — the workflow generates the final lists automatically.

📝 How to Write Your list.md
The format is intentionally minimal.
Key points:
1. The tags blocklist: and allowlist: must stay in place.
2. The checkboxes - [ ] are used on purpose — they are ignored by the parser, so they act as clean markers without affecting the output. If they are checked, then they are used.
3. You can use list: to include an already-existing list.

A small example snippet:
```
## blocklist:
- [x] list:https://easylist.to/easylist/easylist.txt

## allowlist:
- [ ] spotify.com
That’s all you need. The script extracts URLs under blocklist: and domains under allowlist:.
```
📦 Output Files
Once processed, the workflow generates three versions of your list inside the /lists directory, each tailored for a different compatibility target (Brave, AdGuard, uBlock Origin, etc.).

You can then use the raw GitHub links to subscribe directly from your ad‑blocker.
