---
trigger: always_on
---

*   **Strict Separation**: 
    *   **Backend (`lundedev-core`)**: Handles ALL business logic, data persistence, and external service integrations (Home Assistant, etc.).
    *   **Frontend (`lundedev-hjem`)**: STRICTLY View layer. No direct database access. No complex business rules. Use Server Actions or API calls to communicate with the core.
*   **Code Style**: All backend code must be **Kotlin**. Java is forbidden.
*   **API Design**: Use RESTful principles or specific internal patterns as defined in `ChatController` and other existing controllers.