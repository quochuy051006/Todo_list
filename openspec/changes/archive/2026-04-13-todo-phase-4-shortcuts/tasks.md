# Tasks: Todo Phase 4 - Keyboard Shortcuts

## Implementation Plan

### 1. New Task Shortcuts
- [x] Update `toggleState('input')` in `script.js` to add a `keydown` listener to `#todo-input`.
- [x] Logic: If user presses `Enter` on `#todo-input`, call `submitAdd()`.
- [x] Logic: If user presses `Esc` on `#todo-input`, call `toggleState('view')`.

### 2. Inline Edit Shortcuts
- [x] Update `editTodo(id)` in `script.js` to add a `keydown` listener to the `.edit-input` element.
- [x] Logic: If user presses `Enter` on `.edit-input`, call `saveEdit(id, input.value)`.
- [x] Logic: If user presses `Esc` on `.edit-input`, clear `editingId` and call `render()`.

### 3. Checkbox "Enter" Bugfix
- [x] Update the `forEach` loop in `render()` in `script.js`.
- [x] Logic: Add a `keydown` listener to the `.status-checkbox` element.
- [x] Logic: If user presses `Enter` on the focused checkbox, call `toggleTodo(id)`.

### 4. Verification
- [x] Verify `Enter` works for adding tasks without clicking "Add Task".
- [x] Verify `Esc` works for cancelling "Add Task" mode.
- [x] Verify `Enter` works for saving an inline edit.
- [x] Verify `Esc` works for cancelling an inline edit without saving.
- [x] Verify `Enter` correctly toggles a focused checkbox (use `Tab` to navigate to it).
- [x] Verify `Enter` and `Esc` **do not** perform any actions in the Delete Confirmation modal (security safety).
