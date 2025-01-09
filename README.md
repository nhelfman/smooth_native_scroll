# smooth_native_scroll
Repro to demonstrate a user experience issue when doing smooth native scrolling. 

## Description
The demo implement a simple virtual scrolling experience inside a DOM element:
1. Block areas are added to the viewport dynamically based on the `scroll` event
2. The areas are in 3 colors - red, green, blue
3. DOM elements get removed when they exit the scrollable element viewport (to keep DOM size small)

(most logic is in `onViewportChange` function).

## Demo
Try demo here: https://nhelfman.github.io/smooth_native_scroll/

**Issue**: during scrolling, white areas appear in the background although no white content was added to the DOM - we expect to see only red, green and blue areas.

(!) This is not always happening and can depends on different environment factors like screen / display settings / slow CPU / ....

![alt text](image.png)

## Investigation Files
- `simple_scroll_demo_white_areas_Trace-20250109T113258.json`
  Chromium DevTool profling capture while the issue is happening
- `simple_composite_scroll_trace.perfetto_trace.gz`
  Perfetto trace file while the issue is happening
