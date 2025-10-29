# Spicy Jeopardy

A lightweight browser game inspired by Jeopardy that you can self-host or publish on GitHub Pages.

## Getting started locally

Because the project is a static HTML app you do not need any build step—just serve the files. One option that is available on any machine with Python installed is the built-in HTTP server:

```bash
python3 -m http.server 8000
```

Then navigate to [http://localhost:8000/index.html](http://localhost:8000/index.html) in your browser to play the game. The `game.html` file contains the same experience without the landing page if you want to link directly to the board.

If you prefer another static-file server (for example `npx serve` or `php -S localhost:8000`), feel free to use it instead—the only requirement is that the HTML files are available over HTTP so the browser can load them.

## Publishing with GitHub Pages

This repository now includes a GitHub Actions workflow that uploads the root of the project to GitHub Pages whenever you push to the `main` branch. To finish the setup:

1. Go to **Settings → Pages** in your GitHub repository and ensure that "GitHub Actions" is selected as the deployment source.
2. Commit and push your changes to the `main` branch. The workflow defined in [`.github/workflows/deploy.yml`](.github/workflows/deploy.yml) will package the site and publish it.
3. Once the action completes you will receive a link to the live site in the workflow summary. The deployed site will include both `index.html` and `game.html`.

### Triggering a manual publish

You can redeploy at any time from the **Actions** tab by selecting the "Deploy static site" workflow and clicking **Run workflow**.

## Repository structure

```
.
├── index.html   # Landing page that includes the full game
├── game.html    # Alternate entry point directly into the game
└── README.md    # Documentation and deployment instructions
```

Feel free to customize the HTML files with your own categories, questions, and styling to create your own flavor of Spicy Jeopardy!
