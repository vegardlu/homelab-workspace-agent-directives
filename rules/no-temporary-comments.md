
# No Temporary Comments ("For Now")

We strictly avoid comments that describe temporary solutions, "for now" logic, or admit to technical debt inline without a plan.

## The Rule
*   **Do not use phrases like:** "for now", "temporary fix", "simple list... but", "hack", "todo later".
*   **State what IS, not what MIGHT BE.** Comments should explain the current functionality, not apologize for it or describe what is missing.
*   **If it's temporary, fix it.** If code is "temporary", either implement the proper solution immediately or create a formal issue in the issue tracker. Do not leave "for now" comments in the code.
*   **Minimal comments.** Prefer self-documenting code. Comments should explain *why*, not *what*.

## Example
**BAD:**
```kotlin
// We might want a map here, but for now a simple list is enough
val items = listOf<String>()
```

**GOOD:**
```kotlin
val items = listOf<String>()
```
