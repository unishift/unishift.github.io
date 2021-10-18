---
title: '![](/images/gsoc-logo-small.png) GSoC 2019: 360° Video Filter for FFmpeg'
collection: projects
permalink: /project/2019-08-26-gsoc-ffmpeg
excerpt: 'Project’s goal was to write a "v360" filter which would be able to convert 360° videos between various formats and also apply operations like FoV extraction and rotation.'
date: 2019-08-26
---

# Intro

[FFmpeg](https://ffmpeg.org/) is a big and comprehensive video processing framework.
Besides others its awesome features it also has a huge variety of video filters: from basics like rotation to complex neural-network-based like super-resolution.
For this project, I decided to implement a full-fledged filter for 360° video formats conversion, a tool I also needed in my research area.

![](/images/gsoc-2019-vis.png)

# Summer

There was already a baseline filter that I needed to improve.
The baseline filter had a lot of hardcoded conversions between formats, and it would be a pain to extend it with new ones.
So I unified the interface so for any format needed only functions to convert format coordinates to cartesian coordinates and vice versa.

Following this, I continued to improve on filter code and functionality.
I implemented several formats like EAC (used in YouTube) and barrel (used in Facebook), and several interpolation methods.
By the end of the summer, the filter was feature complete and was ready to merge into main branch of FFmpeg.

v360 filter provides functionality to convert videos between the various 360° formats including: equirectangular projection, regular cubemaps, Equi-Angular cubemap (EAC), dual fisheye, barrel. The filter supports FoV extraction, rotation, and mirror operations. Several interpolation methods (nearest neighbor, bilinear, bicubic, and Lanczos) were examined and implemented. The filter is designed to be easily extendable with new formats and interpolation methods. 

# Results

 - Code for conversion was merged into FFmpeg: [commit link](https://git.ffmpeg.org/gitweb/ffmpeg.git/commit/b26094e217d4d7cb9947d25f01c04badb8ba62dd)
 - Documentation is published on FFmpeg website: [docs link](https://ffmpeg.org/ffmpeg-filters.html#v360)

# Acknowledgements

I'd like to thank:

 - my mentor, **Paul B Mahol** for instructing me and helping with code quality and feature planning,
 - **Google** for running GSoC and creating opportunities to join open-source.
