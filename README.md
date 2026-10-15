# Student Management System (DIWA2110)

A simple React app to view, add, edit and delete students. Data is saved in the browser with `localStorage`.

The app starts empty. Every student, including the course of study, is typed in by the user.

## How to run
```
npm install
npm run dev
```

## Files
- `src/components/Navbar.jsx`: the top navigation bar (switches between Dashboard and Students)
- `src/components/Dashboard.jsx`: home page with totals and shortcut buttons
- `src/App.jsx`: holds the state (student list, which modal is open) and the add / edit / delete functions
- `src/components/StudentTable.jsx`: shows the students in a table (and the empty message)
- `src/components/StudentForm.jsx`: the add / edit modal with validation
- `src/components/DeleteModal.jsx`: the delete confirmation modal

## Data types
- A student is an **object**; the list of students is an **array** of objects.
- `id`, `name`, `email`, `course` are **strings**. `age` is a **number**. `enrolled` is a **boolean** (true/false).
- Form inputs give text, so `age` is converted with `Number()` and `enrolled` is converted to a boolean before saving.

## Variable declarations
- `const`: for values that are never reassigned (the starting list, functions, state values).
- `let`: for values that change, like `highest` in the add function and `found` in `validate()`.
- `var`: used once (`emailPattern` in `validate()`) to show the older style. It is function-scoped; `let` and `const` are block-scoped.

## Functions and array methods
- `map()` shows every student as a row, and swaps in an edited student.
- `filter()` removes a deleted student.
- `some()` checks for a duplicate email.
- `forEach()` finds the highest ID number.

## Validation
Name required, course required, age required and between 16 and 100, email required, correctly formatted and not already used.

## Testing
| Test | Result |
|---|---|
| Add a valid student | |
| Add with empty fields (errors shown) | |
| Age 10 or 150 (error shown) | |
| Bad email like `abc` (error shown) | |
| Edit a student | |
| Cancel add / edit / delete | |
| Delete a student | |
| Delete all (empty message shows) | |
| Refresh the page (data stays) | |
| Navbar switches between Dashboard and Students | |
| Dashboard totals update after add / delete | |
| Search by name (and no-match message) | |

## Deployment
Pushed to GitHub and deployed with Vercel or Netlify (build command `npm run build`, output folder `dist`).
