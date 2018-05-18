---
layout: project
title: Depixelize Pixelart
meta: An algorithm that converts pixel art images to beautiful resolution-independent vector representation.
category: project
image: dp-cover.jpg
---

Pixelart is a form of digital art, created through the use of raster graphics software, where images are edited on the pixel level.

The algorithms interpret each pixel of the pixel art and convert them into regions that can be drawn using piecewise-smooth curves. An implementation of the algorithm stated in ['Depixeizing Pixel Art'](http://johanneskopf.de/publications/pixelart/) by Johannes Kopf and Dani Lischinski published in SIGGRAPH 2011.

Algorithm -

*   Input the image
*   Initialize the similarity graph on the basis of pixel colors
*   Resolve crossing edges using different heuristics (planarizing the graph)
*   Create voronoi regions using the similarity graph
*   Extract B-spline curves and optimize

#### Gallery -

{% include figure.html src='dp-input-dolphin.jpg' caption='Upscaled input image' %}
{% include figure.html src='dp-sim-dolphin.jpg' caption='Similarity graph based on color and edges' %}
{% include figure.html src='dp-voronoi-dolphin.jpg' caption='Reshaping each cell' %}
{% include figure.html src='dp-bspline-dolphin.jpg' caption='Output image' %}
