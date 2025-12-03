---
title: "3D Scanning"
category: "Hardware & Design"
image: "/images/featured/3D-scan.png"
layout: "project"
date: 2024-01-04
---

{{< img-text title="Intro" >}}
In this project, I'll walk through the process I used for 3D scanning an object. I used a **Simscan 3D scanner** to capture the data and then analyzed it using **GOM Inspect** software. My goal was to create an accurate 3D model that I could then inspect and measure.
{{< /img-text >}}

{{< chapter title="01. The Scanning Process" subtitle="From Reality to Digital" >}}

{{< img-text title="Getting the Object Ready" src="/images/Brush_rdy.jpg" size="portrait" >}}
First, I had to prepare the brush for scanning. I stuck small, reflective dots (markers) all over the brush, the turntable it's on, and the reference spheres. 

These markers are essential, as they helped my scanner track its position and perfectly align all the scans later.
{{< /img-text >}}

{{< img-text title="Scanning the Brush" >}}
These images show the actual scanning in progress. As I moved the scanner around the brush, I could see the 3D model (the "mesh") being built on the screen in real-time. This live feedback was great because it showed me exactly which parts I've captured and if I've missed any spots.
{{< /img-text >}}

{{< gallery-row src1="/images/Sken1.jpg" src2="/images/Sken2.jpg" >}}

{{< img-text title="Joining the Scans" src="/images/Sken_join.jpg" reverse="true" >}}
To capture the entire object, I scanned it in a few different parts (like the top and bottom). In this step, I "stitched" those individual scans together to make one complete model. 

The bristles were the most challenging part due to their thin and complex geometry. However, I focused mainly on getting clean data for the solid body—the handle and the head. After merging, I had one unified 3D model ready for export as an STL file.
{{< /img-text >}}

{{< chapter title="02. Data Analysis" subtitle="GOM Inspect" >}}

{{< img-text title="Analyzing the 3D Model" src="/images/Smetak obsah.png" >}}
After exporting the finished model, I imported it into GOM Inspect for analysis. In this image, I'm using the software to calculate the total surface area of the scanned brush, which came out to **33,522.27 mm²**.
{{< /img-text >}}

{{< img-text title="Measuring Dimensions" src="/images/Smetak max velikost.png" reverse="true" >}}
GOM Inspect is also great for taking precise measurements. Here, I measured the brush's total length. I used the "2-Point Distance" tool to select the two furthest points on the model, which gave me a total length of **279.809 mm**.
{{< /img-text >}}

{{< img-text title="Specific Features" src="/images/Smetak libovolny rozmer.png" >}}
Finally, I wanted to show how I can measure any specific feature. In this last image, I'm checking the width of the handle at a specific point. The software told me the exact width was **35.704 mm**. This shows how useful the 3D model is for reverse engineering.
{{< /img-text >}}

{{< chapter title="03. Reverse Engineering" subtitle="Next Steps" >}}

{{< img-text title="Reworking in CAD" >}}
The scanned STL file is a perfect "snapshot" but not an editable design. So, for the next phase, I imported this mesh into my CAD software to **reverse engineer** it.

I used the scan as a 3D blueprint. By creating 2D sketches and tracing the key outlines, I gradually rebuilt the object using standard CAD features. Now I have a complete, parametric model—a true digital twin.
{{< /img-text >}}
