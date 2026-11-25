# Multi-Zone Color Monitor

[![Live demo](https://img.shields.io/badge/demo-GitHub%20Pages-2ea44f)](https://jl7121021.github.io/color-monitor/)
[![Repository](https://img.shields.io/badge/GitHub-JL7121021%2Fcolor--monitor-181717?logo=github)](https://github.com/JL7121021/color-monitor)

Watch 1–3 screen areas in real time using browser screen sharing. Set sensitivity thresholds, trigger alarm sound/banners, schedule monitoring, and switch visual themes. Everything is in a single HTML file — no backend, no dependencies, no build step.

> This repo contains only the latest version, **v2.9.6**. Older versions are not included.

- **Live demo:** <https://jl7121021.github.io/color-monitor/>
- **Source code:** <https://github.com/JL7121021/color-monitor>

## Features

- Up to three independently monitored zones, each pausable
- **Precision point** sampling: exact 1 px, including all four screen corners; the crosshair center is transparent so it never covers the sampled pixel
- **Area average** sampling: average RGB over a region
- Sensitivity threshold (1–50%) with live color-delta percentage
- Alarm sound and banner (must be cleared with **Dismiss alarm**)
- Start/stop scheduling (browser policy still requires one manual click when a schedule fires)
- EN / zh-HK switching at runtime (defaults to English)
- 8 visual styles (defaults to Neumorphism) with a header `Dark / Light` toggle that applies to all of them, plus saved/exportable/importable looks
- Header controls stay compact and ordered `UI | Dark / Light | EN / zh-HK | ?`; the `?` help is a bare glyph with no button frame
- Three-step on-screen coach mark with Previous/Next controls; Step 2 stays until you press Next, and the guide can be reopened from the bottom-centre `Guide` / `指引` button after dismissal
- Step 2 explains how to drag the crosshair onto the pixel to sample: the zone number and live sampled RGB color are shown at the crosshair
- First sample waits for two fresh decoded video frames, so the initial color and baseline are correct
- Built-in self-test: five checks with no alarm side effects
- Long-running health monitoring: last sample time (`HH:MM:SS`) with a flashing dot on each completed sample, stall watchdog, 10-minute heartbeat log, and automatic resync when the tab becomes visible
- In-app guide with GitHub repo and ★ Star links visible in both languages; close it with the sticky top-right ✕, Esc, or a click on the backdrop
- In-app version history is collapsed by default, hides dates, and shows a ▾ / ▴ disclosure arrow (click the version tag in the header)
- Visual polish: no repeated grid/dots page texture, restrained sub-card corner radii, and a single top-left light source shared by the centre stage and right sidebar in Neumorphism

## Usage

1. Open the [live demo](https://jl7121021.github.io/color-monitor/) or run it from `localhost`.
2. Click **Start screen share**.
3. Choose a tab, window, or the whole screen in the browser picker.
4. Drag the dashed probe or zone box onto the target. In precision mode you can simply click to place it.
5. Adjust sensitivity and interval. Run **Self-test** any time to verify the pipeline.

### Keyboard shortcuts

| Key | Action |
| --- | --- |
| Arrow keys | Nudge the selected zone/probe |
| Shift + Arrow | Larger step; resize in area mode |
| Wheel / `+` / `-` | Zoom the preview |
| Drag the background while zoomed | Pan the preview |

## Requirements

- Latest Chrome or Edge recommended.
- `getDisplayMedia` requires **HTTPS or localhost**. GitHub Pages satisfies this. Opening the file directly with `file://` may be blocked by some browsers.
- Safari has a compatibility fallback for `<dialog closedby>`.

## Privacy

All settings, themes, and zone coordinates are stored only in your own browser's LocalStorage (prefix `job-monitor-v282-`, kept for backward compatibility). There is no server, no upload, no analytics, and no tracking.

## Files

| File | Purpose |
| --- | --- |
| `index.html` | Full application, v2.9.6 |
| `CHANGELOG.md` | Change history |
| `LICENSE` | MIT license |
| `.gitignore` | Git ignore rules |

## GitHub Pages

This site is published from the `main` branch at `/ (root)`:

<https://jl7121021.github.io/color-monitor/>

To reproduce it, go to **Settings → Pages → Build and deployment**, choose **Deploy from a branch**, select `main` and `/ (root)`, then save.

## Support

If this tool saves you time, star the repo or open an issue with feedback:

<https://github.com/JL7121021/color-monitor>

## License

See [LICENSE](LICENSE) (MIT).
