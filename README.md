# danielbarral-website

Source for [www.danielbarral.com](https://www.danielbarral.com), Daniel Barral's personal site. It links to his projects and games.

It is a static site (plain HTML and CSS, no build step) hosted on GitHub Pages. The custom domain is set in `CNAME`.

## Structure

| File | Page |
|---|---|
| `index.html` | Home (`/`) |
| `games.html` | Games (`/games`), with screenshots and itch.io links |
| `easy-game-maker.html` | [EasyGameMaker](https://www.easygamemaker.com) (`/easy-game-maker`) |
| `create-online-games.html` | [Create Online Games](https://www.createonlinegames.com) (`/create-online-games`) |
| `draw-js.html` | [DrawJS](https://drawjs.app) (`/draw-js`) |
| `image-online-tools.html` | [ImageOnlineTools](https://www.imageonlinetools.com) (`/image-online-tools`) |
| `max-online-tools.html` | [Max Online Tools](https://www.maxonlinetools.com) (`/max-online-tools`) |
| `style.css` | Styles shared by every page |
| `img/` | Product logos, and game screenshots in `img/game-images/<game>/` |
| `favicon.svg`, `apple-touch-icon.png` | Site icon (the PNG is a 180px render of the SVG) |

The menu links leave off `.html` (for example `/games`). GitHub Pages serves `games.html` for those URLs. When you open a file straight from disk, those menu links don't work.

## Editing

- **Add a game:** put its screenshots in `img/game-images/<game>/` as WebP, then copy one of the `<article class="game">` blocks in `games.html`. The main image and the first thumbnail use the same file; mark that thumbnail `aria-pressed="true"` and the rest `"false"`. Give each image an `alt` describing it, and `loading="lazy"`. To convert a PNG: `ffmpeg -i shot.png -c:v libwebp -quality 90 shot.webp`. You can also add a tile to the Games section in `index.html` (the home page shows four).
- **Each page's `<head>`** has a meta description and link-preview (Open Graph) tags with that page's URL. Update them when you change a page or add one.
- **Add a page:** copy an existing page (a product page such as `draw-js.html` is the simplest), and add its link to the `<nav class="menu">` block in **every** page. The header and footer are repeated in each file. On the new page, move `aria-current="page"` to its own menu link, which highlights it. For a new product, also add a card to the Projects grid in `index.html`.
- **Colors** are set as variables at the top of `style.css`, once for light mode and once for dark mode (the site follows the visitor's system setting).
- **Preview locally:** run `python -m http.server` in the repo folder and open http://localhost:8000.
