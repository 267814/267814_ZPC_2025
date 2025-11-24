---
title: "3D scanning"
date: 2021-12-18T11:10:36+08:00
draft: false
language: en
featured_image: /images/featured/3D-scan.png
summary: In this mini-project we were introduced to 3D scanning, using portable scanner.
description: In this mini-project we were introduced to 3D scanning, using portable scanner.
author: 
authorimage:
categories: blog
tags: ["Mini-project"]
---

# Intro

***

---

___

In this project, I'll walk through the process I used for 3D scanning an object. I used a Simscan 3D scanner to capture the data and then analyzed it using GOM Inspect software. My goal was to create an accurate 3D model that I could then inspect and measure.

## Getting the Object Ready

***

---

___

First, I had to prepare the brush for scanning. I stuck small, reflective dots (markers) all over the brush, the turntable it's on, and the reference spheres. These markers are essential, as they helped my scanner track its position and perfectly align all the scans later.

<p align="center">
  <img src="/images/Brush_rdy.jpg" alt="Tripod scheme" class="rounded-2xl shadow-lg" width="600">
</p>

## Scanning the Brush

***

---

___

These images show the actual scanning in progress. As I moved the scanner around the brush, I could see the 3D model (the "mesh") being built on the screen in real-time. This live feedback was great because it showed me exactly which parts I've captured and if I've missed any spots.

<div class="flex flex-col md:flex-row gap-4 mb-8">

  <div class="flex-1 md:w-1/2">
    <img 
      src="/images/Sken1.jpg" 
      alt="Popis prvního obrázku" 
      class="rounded-2xl shadow-lg w-full h-auto">
  </div>

  <div class="flex-1 md:w-1/2">
    <img 
      src="/images/Sken2.jpg" 
      alt="Popis druhého obrázku" 
      class="rounded-2xl shadow-lg w-full h-auto">
  </div>

</div>

## Joining the Scans

***

---

___

To capture the entire object, I scanned it in a few different parts (like the top and bottom). In this step, I "stitched" those individual scans together to make one complete model. The software used the markers I had placed earlier to line everything up perfectly.

As you could see in the scans, the bristles were the most challenging part. They are very thin, dark, and complex, which makes them difficult for a 3D scanner to capture perfectly. However, this wasn't a major problem for my project. I knew a perfect scan of every single bristle wasn't that important because it would be much easier to model them from scratch later in CAD using a simple "pattern" feature. I mainly focused on getting clean, accurate data for the solid body—the handle and the head.

After merging, I had one unified 3D model of the main body, ready to be exported as an STL file.

<p align="center">
  <img src="/images/Sken_join.jpg" alt="Tripod scheme" class="rounded-2xl shadow-lg" width="600">
</p>

## Analyzing the 3D Model

***

---

___

After exporting the finished model, I imported it into GOM Inspect for analysis. In this image, I'm using the software to calculate the total surface area of the scanned brush, which came out to 33,522.27 (mm²).

<p align="center">
  <img src="/images/Smetak obsah.png" alt="Tripod scheme" class="rounded-2xl shadow-lg" width="600">
</p>

## Measuring the Overall Length

***

---

___

GOM Inspect is also great for taking precise measurements. Here, I measured the brush's total length. I used the "2-Point Distance" tool to select the two furthest points on the model—from the end of the handle (Point 1) to the tip of the brush head (Point 2)—which gave me a total length of 279.809 mm.

<p align="center">
  <img src="/images/Smetak max velikost.png" alt="Tripod scheme" class="rounded-2xl shadow-lg" width="600">
</p>

## Measuring Specific Features

***

---

___

Finally, I wanted to show how I can measure any specific feature. In this last image, I'm checking the width of the handle at a specific point. By selecting two points (Point 3 and Point 4) on opposite sides, the software told me the exact width was 35.704 mm. This shows how useful the 3D model is for pulling any specific measurement I need.

<p align="center">
  <img src="/images/Smetak libovolny rozmer.png" alt="Tripod scheme" class="rounded-2xl shadow-lg" width="600">
</p>

# Reworking the Scan in CAD

***

---

___

The scanned STL file I created is a perfect, highly accurate "snapshot" of the brush, but it's not an editable design. It's just a "skin" made of millions of triangles. So, for the next phase of my project, I imported this mesh into my CAD software. My goal here was to reverse engineer it, or in other words, turn that static scan data back into a "living" solid model I could actually edit.

I used the scan as a 3D blueprint. By creating 2D sketches on different planes and tracing the key outlines of the brush's handle and head, I gradually rebuilt the object using standard CAD features (like extrudes, lofts, and fillets). As I mentioned, I also modeled the simplified bristles from scratch. Now I have this complete, parametric model—a true digital twin—and I can easily modify the design, like changing the handle's grip or preparing a new version for 3D printing.