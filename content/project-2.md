---
title: "2D Graphics & Design"
category: "Art & Design"
image: "/images/2d-main.jpg"
layout: "project"
date: 2024-01-02
---

{{< img-text title="Introduction" >}}
This module focused on the fundamentals of 2D computer-aided design (CAD) and computer-aided manufacturing (CAM). Divided into two segments—Vinyl Cutting and Laser Cutting—the primary objective was to master vector graphics and the workflow required to translate digital sketches into physical objects.
{{< /img-text >}}

{{< chapter title="01. The Plotter" subtitle="Vinyl Cutting & Stickers" >}}

{{< img-text title="The Concept & Sketch" src="/images/prototyp-loga.jpg" size="tiny" >}}
The ideation phase began with analog sketching on paper. I aimed for a classic, reusable branding element, specifically a monogram combining my initials, JH. The concept involved interlocking the letters to create a unified symbol that could serve as a personal logo for future applications.
{{< /img-text >}}

{{< img-text title="Vectorizing in Inkscape" src="/images/proces-loga.jpg" reverse="true" >}}
To digitize the sketch, I imported a reference photo into Inkscape (though I would recommend Affinity Designer for a smoother workflow in the future). I traced the raster image to create editable vector paths. During this process, I deviated slightly from the original sketch, connecting the 'J' and 'H' with a single continuous stroke for a cleaner, more modern aesthetic. The output was saved as an SVG, ensuring the design relies on mathematical coordinates rather than pixels, allowing for infinite scalability without quality loss.
{{< /img-text >}}

{{< img-text title="Final Product" >}}
The fabrication involved cutting the design on a vinyl plotter using adhesive paper. I selected a vibrant red vinyl for high contrast and applied the resulting sticker to my laptop charger. The versatility of the vector file allowed me to repurpose the logo across various media, including business cards and, most notably, as this website’s favicon.
{{< /img-text >}}

{{< gallery-row src1="/images/vyriznuty-logo.jpg" src2="/images/vuzite-logo.jpg" >}}


{{< chapter title="02. Laser Cutter" subtitle="Cardboard Prototyping" >}}

{{< img-text title="From 3D to 2D" >}}
The assignment required designing a press-fit construction kit from cardboard. I started by modeling a custom Christmas tree in a 3D CAD environment. The assembly consisted of three intersecting tree sections and a base. Modeling in 3D first was crucial for validating tolerances and ensuring a proper interference fit between the components before cutting any material.
{{< /img-text >}}

{{< 3d-model title="3D Assembly Concept" src="/models/tree.glb" >}}
Designing it as a complete piece first was crucial to check tolerances.
{{< /3d-model >}}

<div class="grid grid-cols-1 md:grid-cols-2 gap-8 w-full">
    <div>
        {{< 3d-model title="Base Part" src="/models/base.glb" >}}
        {{< /3d-model >}} 
    </div>
    <div>
        {{< 3d-model title="Tree Part" src="/models/part.glb" >}}
        {{< /3d-model >}} 
    </div>
</div>


{{< img-text title="Exporting DXF Files" >}}
Once the 3D geometry was finalized, I projected the faces onto a 2D plane and exported them as DXF files. The DXF format serves as the standard for defining 2D toolpaths for the laser cutter. Like SVGs, these files utilize vector data, ensuring that the machine follows precise mathematical curves rather than pixelated approximations.
{{< /img-text >}}

{{< gallery-row src1="/images/DXF-base.jpg" src2="/images/DXF-tree-parts.jpg" fit="contain" >}}


{{< img-text title="The Process & Result" >}}
I imported the files into the laser cutter’s control software and performed nesting to optimize material usage on the cardboard sheet. The machine operation involved both vector cutting for the outline and raster engraving for the text "Christmas 2025" on the base. The final assembly fit together perfectly without glue, validating the efficiency of digital prototyping in the design process.
{{< /img-text >}}

{{< media-row video="/images/Cut-proces.mp4" image="/images/cardboard-tree.jpg" >}}