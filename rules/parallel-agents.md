# Parallel Agent Workflow (Google Antigravity)

When multiple instances of Google Antigravity (or other AI agents) are operating in parallel within this project, adhere strictly to the following best practices:

## 1. Scope Isolation & Boundaries
- **Respect Domain Boundaries**: Never modify files outside your explicitly assigned scope. For example, if assigned to the frontend (`lundedev-hjem`), do not touch the backend (`lundedev-core`) or MCP (`lundedev-random-mcp`) unless instructed.
- **No Shared File Modifications**: Avoid modifying shared configuration files (e.g., root `compose.yaml`, root `.gitignore`, global GitHub Actions workflows) unless you have confirmed no other agent is working on them.
- **Atomic Work**: Break work down so that each agent can complete its task without waiting on or interfering with another agent's output.

## 2. Git & Version Control
- **Frequent Syncs**: Always `git pull origin main` (or the relevant branch) before starting a new task and before committing, to minimize merge conflicts with other agents.
- **Granular Commits**: Commit changes locally as soon as a logical unit of work is completed.
- **Avoid Force Pushes**: Never use `git push --force`.
- **Branching**: If doing major features, consider asking the user if a separate branch is preferred to avoid `main` branch collisions.

## 3. Execution & Testing
- **Port Collisions**: Be aware that another agent might be running a server or test suite. If you start a service, ensure it does not conflict with standard ports (e.g., 3000, 8080) if another agent might be testing them.
- **Idempotent Commands**: Prefer commands that are safe to run concurrently. For example, instead of running a full build/test suite that might lock a directory (`./gradlew test`), consider running specific test classes if sufficient, or be prepared to retry if a lock file issue occurs.
- **Database / State**: Avoid making destructive or schema-altering database changes (via Flyway or direct queries) while another agent might be testing or relying on the current schema.

## 4. Communication
- If a task requires modifying a core shared file (like database schemas, `.agent` rules, or API contracts), stop and use the `notify_user` tool to confirm if it's safe to proceed relative to other ongoing agent work.
- State clearly what you have modified in your final summary or walkthrough so the user can synchronize contexts between parallel agents if needed.
