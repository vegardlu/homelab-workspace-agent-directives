---
trigger: always_on
---

# Technology Stack & Standards

## Backend: `lundedev-core`
-   **Language**: Kotlin (latest stable).
-   **Framework**: Spring Boot.
-   **Build Tool**: Gradle (Kotlin DSL).
-   **Testing**: JUnit 5, MockK.

## Frontend: `lundedev-hjem`
-   **Framework**: Next.js (App Router).
-   **Language**: TypeScript / TSX.
-   **Styling**: Tailwind CSS (Verify version in `package.json`, avoid deprecated classes).
-   **Icons**: Lucide React.
-   **State Management**: React Server Components (RSC) where possible, Client Components only when interactivity is needed.

## Infrastructure
-   **Containerization**: Docker (Distroless images where possible).
-   **Orchestration**: Docker Compose.
-   **Reverse Proxy**: Cloudflare Tunnel / Zero Trust.
