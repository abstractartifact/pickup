[README.md](https://github.com/user-attachments/files/22649876/README.md)
# Pickup Soccer Lineup Helper

Single-file web app for balancing pickup soccer teams.

**Features**
- No GKs. 2 teams until 20 active players, then 4 teams.
- Attendance toggles (IN/OUT) + bulk All active / All out.
- Teams-tab **Reshuffle** that varies assignments while staying balanced.
- When switching to 4 teams, it **splits existing A/B** sides into **A/C** and **B/D** instead of starting over.
- CSV import/export with optional `active` column.

## Deploy on GitHub Pages
1. Create a new GitHub repo (public is fine). Name it e.g. `pickup-lineup`.
2. Upload `index.html` (and this `README.md` if you want).
3. Go to **Settings → Pages**.
   - **Source:** “Deploy from a branch”
   - **Branch:** `main` and **/ (root)`
   - Click **Save**.
4. Your site will publish at `https://<your-username>.github.io/<repo-name>/`

## Using the app
- Add/Import players on the **Roster** tab. Toggle IN/OUT to mark attendance.
- Go to **Teams** to see the auto-balanced split.
  - < 20 active → 2 teams (A/B) and the mapping is saved locally.
  - ≥ 20 active → 4 teams where A→A/C and B→B/D.
- **Reshuffle** (on Teams or Roster) to vary lineups.
- **Export teams** to CSV to share matchups.

## CSV format
```
name,skill,position,stamina[,active]
Eli,3,DEF,3,1
General,3,DEF,2,1
...
```
- `position` in {ANY, DEF, MID, FWD}
- `skill` 1–5, `stamina` 1–3
- `active` accepts `1/0`, `true/false`, `yes/no` (optional; default is active)

## Tips
- **Mobile:** Open the site and “Add to Home Screen” for one-tap access.
- **Privacy:** All roster data is stored in your browser’s localStorage; nothing is sent to a server.
- **Reset mapping:** Use **Clear roster** (or wipe browser storage for the site) to reset A/B memory.
  Import your CSV again if needed.
