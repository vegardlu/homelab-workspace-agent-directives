---
description: Deploy Lundedev Hjem (Frontend)
---

1. Navigate to the frontend project directory
   - Command: `cd /Users/vegard/homelab-workspace/lundedev-hjem`

2. Run local verification
   - Command: `npm run lint`
   - Command: `npm run build`

3. Verify git status and push changes if needed
   - Command: `git status`
   - If there are uncommitted changes, ask the user if they want to commit and push them.
   - If the local branch is ahead of remote, push the changes: `git push`

4. Wait for GitHub Actions build to complete
   - Command: `gh run watch -i 10 --exit-status`
   - Note: This waits for the latest workflow run to finish. If it fails, the workflow should stop here.

5. Deploy to the server
   - Command: `ssh lundedev "cd homelab && docker compose pull lundedev-hjem && docker compose up -d lundedev-hjem"`
