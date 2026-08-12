# React Dark Mode Toggle

A simple React + Vite project that implements a light/dark theme switcher using React Context and Tailwind CSS v4's class-based dark mode.


## Features

- **Light / Dark Theme Toggle** — switch themes instantly with a single click
- **Built with Vite** — fast dev server and build times
- **Styled with Tailwind CSS v4** — using the new `@custom-variant` approach for class-based dark mode
- **React Context API** — global theme state shared across components without prop drilling
- **Sample Product Card** — demo UI component showcasing dark mode styling in action

## Tech Stack

- [React](https://react.dev/)
- [Vite](https://vite.dev/)
- [Tailwind CSS v4](https://tailwindcss.com/)

## Project Structure

```
src/
├── components/
│   ├── ThemeBtn.jsx     # Toggle switch to change theme
│   └── Card.jsx         # Sample UI card demonstrating dark mode styles
├── context/
│   └── Theme.js          # Theme context, provider, and useTheme hook
├── App.jsx                # Root component holding theme state
├── index.css              # Tailwind import + dark mode variant config
└── main.jsx
```

## How It Works

1. `App.jsx` holds the `themeMode` state (`"light"` or `"dark"`) and two functions, `lightTheme()` and `darkTheme()`, to update it.
2. This state and the two functions are shared with the rest of the app via `ThemeProvider` from `context/Theme.js`.
3. A `useEffect` in `App.jsx` watches `themeMode` and toggles the `light` / `dark` class on the `<html>` element.
4. Tailwind's `@custom-variant dark (&:where(.dark, .dark *));` in `index.css` tells Tailwind to apply `dark:` utility classes whenever an ancestor has the `.dark` class.
5. Any component (like `ThemeBtn` or `Card`) can access and update the theme via the `useTheme()` hook.

## Getting Started

### Prerequisites

- Node.js (v18 or higher recommended)
- npm

### Installation

```bash
git clone <your-repo-url>
cd <project-folder>
npm install
```

### Run the Dev Server

```bash
npm run dev
```

Then open the URL shown in your terminal (usually `http://localhost:5173`).

### Build for Production

```bash
npm run build
```

## Usage

Click the toggle switch in the top-right corner to switch between light and dark mode. The theme is applied instantly across the entire app.
