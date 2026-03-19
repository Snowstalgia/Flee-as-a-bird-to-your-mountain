# Repository Guidelines

## Project Structure & Module Organization
This repository is a static, single-page web project. [`index.html`](C:/Users/黄yx/Flee-as-a-bird-to-your-mountain-main/index.html) contains the HTML, CSS, and JavaScript for scene flow, dialogue, and puzzle interactions. Image assets live in [`images/`](C:/Users/黄yx/Flee-as-a-bird-to-your-mountain-main/images), video assets live in [`videos/`](C:/Users/黄yx/Flee-as-a-bird-to-your-mountain-main/videos), and the custom font is [`xiangcuikesong.ttf`](C:/Users/黄yx/Flee-as-a-bird-to-your-mountain-main/xiangcuikesong.ttf). Keep new story assets in those existing folders and reference them through the `imageAssetRoot` and `videoAssetRoot` helpers.

## Build, Test, and Development Commands
There is no package-based build pipeline in this repo. For local preview, run a simple static server from the repository root:

```powershell
python -m http.server 8000
```

Then open `http://localhost:8000`. Use a server rather than `file://` so the puzzle `fetch()` flow behaves consistently. If you only need a quick file check, open `index.html` directly in a browser.

## Coding Style & Naming Conventions
Follow the existing style in `index.html`: 4-space indentation, semicolons in JavaScript, and grouped sections for CSS and scene logic. Reuse current naming patterns such as `scene-*`, `puzzle-*`, and descriptive handler names like `startChapter1`. Keep asset filenames descriptive and stable; this project already uses Chinese scene-based names such as `第一章-解谜-房间全貌.png`.

## Testing Guidelines
No automated test suite is configured yet. Verify changes manually in a browser:

- confirm scene transitions, dialogue typing, and hotspot clicks
- confirm all referenced images and videos load
- confirm the remote puzzle endpoint responds without console errors

When adding complex logic, prefer extracting it into small functions that can be tested later.

## Commit & Pull Request Guidelines
This branch has no commit history yet, so use clear imperative commit subjects, for example: `Add chapter one bookshelf interaction`. Keep commits focused on one feature or fix. Pull requests should include a short summary, impacted scenes/assets, manual test notes, and screenshots or short recordings for visual changes.

## Configuration Notes
The puzzle flow posts to an external endpoint defined in `index.html`. Do not hardcode secrets in the page. If the endpoint changes, update the constant in one place and retest the puzzle path locally.
