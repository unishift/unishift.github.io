---
title: '![](/images/gsoc-logo.png) GSoC 2021: Equirectangular Projection (ERP) and Cubemap Projection (CMP) conversion'
collection: projects
permalink: /project/2021-08-20-gsoc-libxcam
excerpt: 'The goal of the project was to implement conversion from equirectangular projection of 360° video to cubemap for libXcam library using GLES.'
date: 2021-08-20
---

# Intro

[libXcam](https://github.com/intel/libxcam) is an Intel open-source library designed for diverse image and video processing, such as digital video stabilization, noise reduction, wide dynamic range, and fog removal.
Moreover, the library including specific algorithms for 360° video processing: stitching and automotive surround view stitching.
The library makes use of GPU to optimize algorithms speed.

For Google Summer of Code 2021 library maintainers [proposed](https://01.org/linuxmedia/news/gsoc-2021-ideas) a project to implement equirectangular projection to cubemap conversion into stitching pipeline.
As I have experience with both implementing various 360 video formats conversion (wrote `v360` filter for FFmpeg during GSoC 2019) and calculations via OpenGL, I decided to participate and was [chosen](https://summerofcode.withgoogle.com/projects/#4637812755791872) for the project.

![](/images/gsoc-2021-vis.png)

# Summer

I planned to implement conversion by directly calculating transformation from ERP to CMP and performing remapping to another buffer.
And I needed to do it using GLES and existing library interfaces, so I started to learn the codebase.

At the start of summer, my mentor (maintainer of libXcam) provided video samples and suggested to first look at the stitching interface and stitching executable `test-surround-view`.
During reading the suggested code I noticed that the library has the functionality to generate "topview" which is basically a projection showing what is under a viewpoint (like if you would stay at camera position watching down).
The generation was done by remapping pixels from a buffer with stitched equirectangular projection and supported GLES.
It seemed that I could reuse this functionality for my task.

After remembering conversion equations and implementing them in code a working prototype was done :)
The prototype worked as intended and after approving the method with my mentor I started to clean up code, fix mistakes and handle corner cases.
When I finished with that I created a pull requested and my code was merged into libXcam upstream.

# Results

 - Code for conversion was merged into libXcam: [https://github.com/intel/libxcam/pull/778](https://github.com/intel/libxcam/pull/778)
 - Functionality can be tested using `test-surround-view` executable in the library.

# Acknowledgements

I'd like to thank:

 - my mentor, **Zong Wei** for helping and guiding me with this project,
 - **Google** for running GSoC and creating opportunities to join open-source. 