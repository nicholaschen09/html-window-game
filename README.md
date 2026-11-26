# Window Balls

A small browser game where bouncing balls pass between separate windows, including when those windows are resized.

## Run locally

From this repository, start a local web server:

```sh
python3 -m http.server 8765
```

Open `http://localhost:8765` in a desktop browser. Click **Open window** and arrange the windows side by side. If your browser opens a tab, drag that tab into its own window. Click **Start 24 balls**. Use **Add 12 balls** for more, or **Clear** to reset.

The windows communicate through `BroadcastChannel`, so they must use the same URL origin. Each ball belongs to one window. When its center crosses an edge, that window sends it to the next window in opening order. The receiving window places it at the same relative height. Both windows draw the ball briefly while it straddles the boundary, which softens the handoff. The balls bounce off the top and bottom of their current window and the unlinked outer side edges.

This version does not measure physical screen positions. It works after resizing, but a gap or browser frame between windows remains visible during a transfer.
