# Galaxy Pets — Redeem Codes + Username Uniqueness (Static, GitHub Pages)

- **Account Gate** (local): users must create a demo account before entering (stored in `localStorage`).
- **Coins-only** prices (1 USD = 100 coins). Discord contact: **wkeysilver**.
- **Redeem Codes**: Users can redeem coin codes from `codes.json` (you maintain this file).
- **Username Uniqueness**:
  - **Local**: prevents reusing the same username again on the same device.
  - **Global (best-effort)**: when hosted on GitHub Pages, signup checks your repo’s **GitHub Issues** for `label:user` and a matching issue **title**; if found, it blocks that username.
  - Users can also click **“Reserve Username on GitHub”** (opens a prefilled Issue) to claim it.
  - You can approve/close these Issues to manage reservations.

## Publishing
1. Create a **public** repo and upload these files to the root:
   - `index.html`
   - `codes.json` (edit coin amounts and add/remove codes as you sell them)
   - `.nojekyll`
   - `README.md`
   - `LICENSE`
   - `favicon.svg`
2. **Settings → Pages**: Source **Deploy from a branch**, Branch **main**, Folder **/(root)**.
3. Your site will be at: `https://<your-username>.github.io/<repo-name>/`

## Managing codes
- Edit `codes.json` in GitHub to add or remove codes:
  ```json
  {"GPK-AB12": 500, "GPK-XY99": 1000}
  ```
- After a user redeems a code, delete that entry from `codes.json` (so it can’t be reused).

## Managing usernames
- When a user clicks **Reserve Username**, a new Issue opens with `label:user` and the username as the **title**.
- If a different user tries to register with that exact name, the site’s search will detect the reservation and block it.
- You can maintain reservations by closing/labeling Issues.

Generated on 2025-09-19.
