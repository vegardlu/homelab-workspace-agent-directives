---
trigger: always_on
---

# Coding Standards

- **Strict Separation**:
  - **Backend (`lundedev-core`)**: Handles all business logic, data persistence, and external service integrations (e.g., Home Assistant).
  - **Frontend (`lundedev-hjem`)**: Serves strictly as the view layer. No direct database access or complex business rules are permitted. Use Server Actions or API calls to communicate with the core.
- **Code Style**: All backend code must be written in **Kotlin**. Java is strictly forbidden. The maximum line length is 120 characters.
- **API Design**: Adhere to RESTful principles or specific internal patterns as defined in existing controllers (e.g., `ChatController`).
- **Dependencies**: Always use the most recent stable versions of dependencies. Before adding or updating, you must check `mvnrepository` for backend libraries and `npm`/`package.json` for frontend libraries to confirm the absolute latest stable version. Actively prefer modern, actively maintained libraries over outdated or legacy alternatives.
- **No Temporary Comments**: We strictly avoid comments that describe temporary solutions, "for now" logic, or admit to technical debt inline without a concrete plan.
  - Do not use phrases like: "for now", "temporary fix", "simple list... but", "hack", or "todo later".
  - State what IS, not what MIGHT BE. Comments should explain the current functionality, not apologize for it or describe what is missing.
  - If a solution is temporary, either implement the proper solution immediately or create a formal issue in the issue tracker.
  - Prefer self-documenting code. Comments should explain *why*, not *what*.
