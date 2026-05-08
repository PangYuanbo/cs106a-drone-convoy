# Autonomous Safe Drone Convoy Following · CS 106A

Static one-page site for our EE/CS 106A Spring 2026 final project.

**Live:** https://cs106a-drone-convoy.vercel.app

## What this repo contains

- `index.html` — the entire site (all CSS + JS inline)
- `videos/` — the 5 demo clips referenced in the page (~15 MB)
- `tello-station.sh` — switches a Tello between AP and station mode (real hardware)
- `tt_show_aruco.py` — renders an ArUco marker onto a RoboMaster TT's 8×8 LED matrix
- `assets/` — static images

The actual ROS 2 / Gazebo project source lives in its own repo:
[Tyler6666666/106a_final_project](https://github.com/Tyler6666666/106a_final_project).

## Run locally

```bash
open index.html       # macOS — opens in default browser
# or
python3 -m http.server 8080
```

## Deploy

Hosted on Vercel as a static site. Any commit to `main` redeploys automatically
once the project is linked. Manual deploy:

```bash
vercel --prod
```

## Site structure

1. Hero · live in-browser drone-follower sim
2. Team · 4 contributors
3. Motivation · convoying for UAVs
4. System architecture · animated ROS pipeline (ArUco / Face mode toggle)
5. Core code · auto-playing 5-stage Cursor-Desktop demo
6. Operation · 5-state safety machine
7. Try it online · interactive AR-tag follower (drag + auto-orbit)
8. Live demos · sim + real classroom footage
9. Failures & mitigations · 6 issues we hit
10. Future plans · 4 directions
11. Real-hardware bridges · `tello-station.sh` + `tt_show_aruco.py`
12. Quickstart

— EE/CS 106A · Spring 2026
