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

- **Add a game:** put its screenshots in `img/game-images/<game>/` as WebP, then copy one of the `<div class="gameDiv">` blocks in `games.html`. Give each image an `alt` describing it, and `loading="lazy"`. To convert a PNG: `ffmpeg -i shot.png -c:v libwebp -quality 90 shot.webp`.
- **Each page's `<head>`** has a meta description and link-preview (Open Graph) tags with that page's URL. Update them when you change a page or add one.
- **Add a page:** copy an existing page, and add its link to the `<div class="menu">` block in **every** page. The menu is repeated in each file.
- **Preview locally:** run `python -m http.server` in the repo folder and open http://localhost:8000.
