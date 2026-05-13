# Autonomous Safe Drone Following · CS 106A

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

The page is organized as a static technical case study: story first, proof second, and appendix material last.

1. Hero · what the project is, core metrics, and a real Tello demo loop
2. Project Overview / Introduction · goal, motivation, hardware context
3. Results First · Gazebo, ArUco, and YOLOv8 face-tracking demos
4. System Design · ROS 2 perception → control → Tello actuation pipeline
5. Implementation · hardware, software stack, nodes, topics, and expandable code-stage appendix
6. Control + Safety · visual servoing and 5-state safety machine
7. Failure Modes + Fixes · six real issues with causes and mitigations
8. Future Work / Conclusion · limitations and next steps
9. Team Contributions · major contributions by member
10. Resources / Additional Materials · GitHub, slides placeholder, videos, package appendix, interactive sim, hardware bridges, and quickstart

— EE/CS 106A · Spring 2026
