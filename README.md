# smooth_native_scroll
Repro to demonstrate an issue with user experience when doing smooth native scrolling. 

The demo implement virtual scrolling experience inside a DOM element:
1. Block areas are added to the viewport dynamically based on the `scroll` event
2. The areas are in 3 colors - red, green, blue
3. DOM elements get removed when they exit the scrollable element viewport (to keep DOM size small)

(most logic is in `onViewportChange` function).

Issue: during scrolling, white areas appear in the background although no white content was added to the DOM.

![alt text](image.png)