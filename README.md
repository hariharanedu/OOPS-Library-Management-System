# Library Management System

A browser-based Library Management System built with HTML and vanilla JavaScript. It is a visual, interactive port of a C++ OOP console project, demonstrating core Object-Oriented Programming concepts with a clean, responsive UI.

## Live Demo

Open `index.html` (or `Library_Management_System.html`) directly in any modern web browser — no server or build step required.

## Features

- **Admin Panel** — secure login, add/update books, reduce/delete inventory, view all user records
- **Student & Teacher Login** — register or log in by name and roll number; each role gets a different loan period
- **Borrow / Return / Renew** — full book-issue workflow with manual date entry and overdue detection
- **OOP Flow Visualizer** — real-time step-by-step animation showing which class and method handles each action
- **Light / Dark theme** — toggle persisted for the session
- **Responsive layout** — adapts to mobile and desktop screen sizes
- **Zero dependencies** — runs entirely offline; no npm, no frameworks, no CDN links

## OOP Design

The application mirrors the class structure of the original C++ project:

| Class | Responsibility |
|-------|---------------|
| `Library` | Core controller — holds book and user arrays; exposes `findBook()`, `findUser()`, `addBook()`, `removeBook()`, `issue()`, `acceptReturn()` |
| `Book` | Entity — stores `id`, `title`, `quantity`; exposes `isAvailable()`, `addCopies()`, `takeOne()`, `returnOne()` |
| `User` | Entity — stores `name`, `rollNo`, `hasBook`, `issueDate`, `dueDate`; exposes `login()`, `borrow()`, `return()`, `renew()` |

All data is held in plain JavaScript arrays and searched with linear scan (mirroring the original C++ algorithm).

## Project Structure

```
├── index.html                    # Redirect shim → Library_Management_System.html
└── Library_Management_System.html # Complete single-file application (HTML + CSS + JS)
```

## Getting Started

1. Clone or download the repository.
2. Open `index.html` in any modern browser (Chrome, Firefox, Edge, Safari).
3. Use the main menu to navigate between Admin and User sections.

### Default Admin Credentials

| Field    | Value       |
|----------|-------------|
| Password | `admin123`  |

> These credentials are for assignment/demo purposes only.

### Loan Periods by Role

| Role    | Loan Days |
|---------|-----------|
| Student | 14 days   |
| Teacher | 30 days   |

## Usage Walkthrough

### As Admin
1. Select **Admin** from the main menu and log in.
2. **Add/Update Book** — enter a Book ID, title (for new books), and quantity.
3. **Delete/Reduce Book** — enter a Book ID and the number of copies to remove.
4. **View Records** — see all currently issued books with due dates.
5. **Logout** to return to the main menu.

### As Student / Teacher
1. Select **Student** or **Teacher** from the main menu.
2. Enter your name and roll number to register or log back in.
3. Choose from **Borrow**, **Return**, or **Renew** in your panel.
4. Dates are entered manually in `DD MM YYYY` format (e.g. `25 03 2026`).

## Concepts Demonstrated

- **Encapsulation** — each class owns its own data and exposes a clean method interface
- **Abstraction** — the `Library` class hides internal array management from the UI layer
- **Roles & Polymorphism** — student and teacher users share the same `User` model but receive different loan periods via `loanDaysForRole()`
- **Linear search** — `findBookIndex()` and `findUserIndex()` mirror the O(n) array traversal of the C++ source
- **Manual date arithmetic** — leap-year-aware calendar logic reimplemented in JavaScript (`dateToDays`, `addDays`, `validateDate`)

## License

This project is provided for educational purposes.
