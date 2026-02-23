---
description: Deploy Lundedev Random MCP (Backend)
---

1. Navigate to the project directory
   - Command: `cd /Users/vegard/homelab-workspace/lundedev-random-mcp`

2. Run local tests to ensure code quality
   - Command: `./gradlew test`

3. Verify git status and push changes if needed
   - Command: `git status`
   - If there are uncommitted changes, ask the user if they want to commit and push them.
   - If the local branch is ahead of remote, push the changes: `git push`

4. Wait for GitHub Actions build to complete
   - Command: `gh run watch -i 10 --exit-status`
   - Note: This waits for the latest workflow run to finish. If it fails, the workflow should stop here.

5. Deploy to the server
   - Command: `ssh lundedev "cd homelab && docker compose pull lundedev-random-mcp && docker compose up -d lundedev-random-mcp"`

6. Verify Deployment
   - Command: `ssh lundedev "docker compose ps lundedev-random-mcp"`
   - Check that the container state is 'Up' or 'healthy'.
