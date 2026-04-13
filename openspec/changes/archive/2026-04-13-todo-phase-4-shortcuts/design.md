# Design: Todo Phase 4 - Keyboard Shortcuts

## Implementation Details

### Keyboard Listener Strategy
We will implement an "Event Listener" pattern that focuses on the active context. Since we only want shortcuts for `Enter` and `Esc` when they are most logical, we will use two approaches:

#### 1. Input-Level Listeners
For the Add and Edit inputs, we will add `keydown` listeners directly to the DOM elements. This is the cleanest way to ensure `Enter` only submits when you are actually in those modes.

#### 2. Global Listener (Optional but recommended)
We can add a global `keydown` listener to `window` for `Esc`. This ensures no matter where focus is, pressing `Escape` will clear the current UI "gate" (modal, add, or edit).

### Event-to-Function Mapping

| Key | Event Source | Target Method |
| :--- | :--- | :--- |
| `Enter` | `#todo-input` | `submitAdd()` |
| `Enter` | `.edit-input` | `saveEdit(id, text)` |
| `Enter` | `.status-checkbox` | `toggleTodo(id)` |
| `Esc` | Global / `.edit-input` | `render()` (to cancel edit) |
| `Esc` | Global / `#todo-input` | `toggleState('view')` (to cancel add) |

### Checkbox Interaction Fix
We will update the `forEach` loop inside `render()` to add a `keydown` listener to the `.status-checkbox` element. If the event's `.key` is `"Enter"`, it will call `toggleTodo(id)`.

## Tradeoffs & Considerations
- **Prevent Default:** Use `event.preventDefault()` for `Enter` to ensure we don't accidentally submit any hidden forms or scroll the page unexpectedly.
- **Selection Interference:** Ensure shortcuts don't fire when focus is elsewhere (e.g. if the user expands a future browser extension UI).
