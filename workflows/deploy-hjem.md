---
description: Deploy Lundedev Hjem (Frontend)
---

This workflow automates the deployment of the Lundedev Hjem (Frontend) service. It performs local verification (linting and building), ensures changes are conditionally pushed, waits for GitHub Actions to complete, and updates the Docker container on the server.
Note: Execute all local commands with `Cwd` set to `/Users/vegard/homelab-workspace/lundedev-hjem`. Do not use `cd` commands.

1. Run local verification
   - Command 1: `npm run lint`
   - Command 2: `npm run build`

2. Verify git status
   - Command: `git status`
   - If there are uncommitted changes, ask the user if they want to commit and push them.
   - If the local branch is ahead of remote, push the changes using `git push`.

3. Wait for GitHub Actions build to complete
   - Command: `gh run watch -i 10 --exit-status`
   - Note: This waits for the latest workflow run to finish. If it fails, the workflow should stop here.

4. Deploy to the server
   - Command: `ssh lundedev "cd homelab && docker compose pull lundedev-hjem && docker compose up -d lundedev-hjem"`

5. Verify Deployment
   - Command: `ssh lundedev "docker compose ps lundedev-hjem"`
   - Check that the container state is 'Up' or 'healthy'.