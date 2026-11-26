# Window Balls

A small browser game where bouncing balls move between separate windows according to their positions on your screen.

## Run locally

From this repository, start a local web server:

```sh
python3 -m http.server 8765
```

Open `http://localhost:8765` in a desktop browser. Click **Open window** and arrange the windows side by side. If your browser opens a tab, drag that tab into its own window. Move your pointer inside each window once to calibrate its viewport position, then click **Start 24 balls**. Use **Add 12 balls** for more, or **Clear** to reset.

The windows communicate through `BroadcastChannel`, so they must use the same URL origin. Each ball's position is calculated from its start time and velocity in screen coordinates; no server is needed for the simulation. Balls bounce against the outer bounds of the windows present when each batch starts. They can disappear while crossing a gap between windows and reappear in the next one.
