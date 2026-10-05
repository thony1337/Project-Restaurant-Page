# Hako Restaurant Page

This is my restaurant page project from The Odin Project. The page is for Hako, a Japanese comfort food place in Brasília. I used JavaScript to build everything inside the page, and Webpack to bundle it.

Live site: https://thony1337.github.io/Project-Restaurant-Page/

## What it does

- All the content inside `#content` is created with JavaScript. The HTML only has the header, the nav buttons and an empty div.
- There are two tabs, Home and Menu. Clicking a button clears the page and loads that tab.
- The Home tab has a background photo, the restaurant name, a subtitle and an order button.
- The Menu tab has a photo header and the dishes (Entradas and Bento) with descriptions and prices.
- The "Peça Agora" buttons take you to the Hako page on iFood.

## What I used

- JavaScript (ES modules)
- HTML and CSS
- Webpack, with html-webpack-plugin, style-loader and css-loader
- GitHub Pages for hosting

## How the code is organized

- `template.html`: the HTML skeleton with the nav and the empty `#content` div
- `index.js`: loads the Home tab first and handles the nav button clicks
- `home.js`: builds the Home tab
- `menu.js`: builds the Menu tab
- `styles.css`: all the styling

Each tab is its own module. It exports a function that empties `#content` and then creates and adds the elements for that tab.

## Running it locally

```bash
git clone https://github.com/thony1337/Project-Restaurant-Page.git
cd Project-Restaurant-Page
npm install
npx webpack serve
```

Then open http://localhost:8080.

To build the project, run `npx webpack`. The result goes into the `dist` folder.

## Deploying to GitHub Pages

GitHub Pages looks for `index.html` in the root, but mine ends up inside `dist`. So I push the `dist` folder to its own `gh-pages` branch.

First time only:

```bash
git branch gh-pages
```

Every time I deploy:

```bash
git checkout gh-pages && git merge main --no-edit
npx webpack
git add dist -f && git commit -m "Deployment commit"
git subtree push --prefix dist origin gh-pages
git checkout main
```

In the repo settings, the Pages source needs to be set to the `gh-pages` branch.

## Things I want to add later

- A contact tab
- A layout that works better on phones
- More dishes on the menu
