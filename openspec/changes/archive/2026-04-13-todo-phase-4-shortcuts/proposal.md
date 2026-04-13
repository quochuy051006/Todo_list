# Proposal: Todo Phase 4 - Keyboard Shortcuts & Accessibility

## What are we building?
We are implementing a "Keyboard-First" productivity layer to the Todo App. This includes mapping the `Enter` and `Escape` keys to the most common actions (Submit, Save, Cancel) and fixing an accessibility gap where checkboxes don't respond to the `Enter` key.

## Why are we building it?
- **Speed:** Users shouldn't have to reach for their mouse to save or cancel a task they just typed.
- **Consistency:** Clicking "Edit" or "Add" focuses an input; the natural intuition is to press `Enter` to finish.
- **Accessibility:** Keyboard users who navigate via `Tab` expect `Enter` to toggle a checkbox, just as it does for buttons.

## Scope
- **In-Scope:**
    - `Enter` to submit a new task in the Add area.
    - `Enter` to save an inline edit in the task list.
    - `Enter` to toggle a checkbox when it is focused.
    - `Escape` (Esc) to cancel "Add Mode" and return to the list.
    - `Escape` (Esc) to cancel an "Inline Edit" and revert the row.
