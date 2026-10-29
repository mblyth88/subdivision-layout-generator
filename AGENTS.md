# Rules for this repo
This repo is the master copy of this Meliora tool. GitHub wins over any local or Claude copy.
## Working
- Check the current repo state before editing. GitHub is the source of truth.
- Never commit directly to main. Every change goes on a branch and into a PR.
- Use one branch per task: feature/<name> or fix/<name>.
- Tiny fixes still get a small PR. One-line changes are allowed, but they still go through a PR.
- Only Mitch merges to main. Claude never merges its own PR.
- Keep changes small and on-task. No unrelated refactors or tidy-ups.
- Do not delete or overwrite files without confirming the reason and the current repo state.
- Run checks if the repo already has them; otherwise skip them.
- Bump the tool's version once per PR (patch for fixes, minor for new features) and add one changelog line. Never bump on intermediate builds.
## Meliora specifics
- If the same skill or tool exists in Claude and in GitHub, the GitHub version is authoritative.
- Any change made to a skill in Claude must be copied back to GitHub in the same session.
- No live job data, client details, fees, financials, or sensitive business data in the repo. Keep those in Google Drive.
- Folder paths like C:\MCE\04 JOBS must come only from config/paths.json, for example:
  "jobs_root": "C:\\MCE\\04 JOBS"
  Never hardcode a path in a skill or script.
- Finish with a plain-English summary: what changed, what it means for day-to-day work, and any risk or follow-up item.
## Prototype tools
- If a tool is still experimental, label it EXPERIMENTAL in the README and keep it off main until it is proven.
## Final Guardrail
If a Claude copy and the GitHub repo disagree, follow GitHub and list the difference in the summary so Mitch can decide whether to copy anything back.