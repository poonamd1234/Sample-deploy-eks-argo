# Simple Todo App (Static)

A minimal static web app — plain HTML, CSS, and JavaScript, no build tools, no dependencies, no backend. Great as a GitHub sample repo or a starting point for GitHub Pages.

## Features
- Add tasks
- Mark tasks as done
- Delete tasks
- Live task counter

## Project structure
```
sample-static-app/
├── index.html   # Markup
├── style.css    # Styling
├── script.js    # App logic (in-memory state)
└── README.md
```

## Running locally
No build step required. Just open `index.html` in a browser, or serve it locally:

```bash
# Python 3
python3 -m http.server 8000

# Node (with npx)
npx serve .
```

Then visit `http://localhost:8000`.

## Deploying to GitHub Pages
1. Push this folder to a GitHub repository.
2. Go to **Settings → Pages**.
3. Under **Source**, select the branch (e.g. `main`) and root folder.
4. Save — your app will be live at `https://<username>.github.io/<repo-name>/`.

## Notes
- State is kept in memory only (no `localStorage`/database), so tasks reset on page reload. Swap in `localStorage`, a backend API, or a database if you want persistence.
- No external libraries — everything is vanilla HTML/CSS/JS.

## License
MIT — feel free to use this as a starting template.
