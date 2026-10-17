# Temple Dash

3D Endless Runner Inspired by Temple Run (Built with Three.js, Runs in the Browser)

You grabbed the idol. Now run. Temple Dash is a single-file browser game: dodge walls, slide under beams, jump over pits and collect coins while the temple path speeds up beneath you. No install and no build step. Open `index.html` and play.

## Quick summary

- **Genre:** Endless runner with three lanes, a chase camera and a growing difficulty curve.
- **Engine:** [Three.js](https://threejs.org/) r128 (loaded from cdnjs) with plain JavaScript.
- **Platforms:** Desktop (keyboard) and mobile (swipe and tap).
- **Saves:** Best score is stored in the browser with `localStorage`.

## Controls

| Action | Keyboard | Touch |
| --- | --- | --- |
| Move left / right | `←` `→` or `A` `D` | Swipe left / right |
| Jump | `↑`, `W` or `Space` | Swipe up or tap |
| Slide (or fast fall) | `↓` or `S` | Swipe down |

## Obstacles

| Obstacle | How to beat it |
| --- | --- |
| Stone wall (low) | Jump over it |
| Wooden beam (overhead) | Slide under it |
| Stone block | Switch to a free lane |
| Pit | Jump across it |

Coins are worth 10 points each. Distance counts as 1 point per meter. Speed rises the longer you survive.

## How it works

1. The world is a chain of 8-unit "rows". Each row holds a floor piece, side walls, trees and either a hazard, a pit, or a line of coins.
2. The player stays at the origin. Rows move toward the camera and are removed once they pass it, while new rows spawn at the far end.
3. Each frame the game checks the rows near the player for collisions based on lane, height and slide state.
4. Falling into a pit, or hitting any hazard, ends the run and shows the score screen.

## Run locally

```bash
git clone https://github.com/<your-username>/temple-dash.git
cd temple-dash
# open index.html in your browser
```

The game loads Three.js and fonts from the web, so an internet connection is required. To serve it locally instead of opening the file directly:

```bash
python3 -m http.server 8000
# then visit http://localhost:8000
```

## Deploy with GitHub Pages

1. Push the repo to GitHub.
2. Go to **Settings → Pages**.
3. Under **Build and deployment**, choose **Deploy from a branch**, then select `main` and `/ (root)`.
4. After a minute, the game is live at `https://<your-username>.github.io/temple-dash/`.

## Project structure

```
temple-dash/
├── index.html    # the whole game: markup, styles and JavaScript
├── README.md
├── LICENSE
└── .gitignore
```

## Roadmap

- [ ] Corner turns like the original Temple Run
- [ ] Demon monkeys chasing the player
- [ ] Power-ups (magnet, shield, coin boost)
- [ ] Sound effects and music
- [ ] Global leaderboard

## License

Released under the [MIT License](LICENSE).
