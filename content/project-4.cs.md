---
title: "3D Skenování"
category: "Hardware & Design"
image: "/images/scan-main.jpg"
layout: "project"
---

{{< img-text title="Zachycení reality" src="/images/scan-1.jpg" >}}
Tento projekt se zaměřuje na digitalizaci fyzických objektů pomocí fotogrammetrie a technologie LiDAR. Umožňuje mi to zachovat reálné artefakty nebo provádět reverzní inženýrství dílů, k nimž neexistují CAD data.

Pomocí aplikace Polycam a specializovaného hardwaru zachycuji stovky referenčních bodů pro generování hustého mračna bodů.
{{< /img-text >}}

{{< img-text title="Čištění dat" src="/images/scan-2.jpg" reverse="true" >}}
Surová data ze skenu jsou často nepřesná a obsahují šum. Mesh importuji do **Blenderu**, kde geometrii vyčistím.

Hlavním úkolem je retopologie – vytvoření čisté sítě s nízkým počtem polygonů, která je vhodná pro renderování nebo 3D tisk. Také opravuji chyby v geometrii (non-manifold edges) a uzavírám díry v povrchu.
{{< /img-text >}}

{{< img-text title="Digitální dvojče" src="/images/scan-3.jpg" >}}
Výsledkem je "Digitální dvojče" původního objektu.

Tyto modely lze použít v herních enginech, prostředí VR nebo je vytisknout na 3D tiskárně a vytvořit tak repliku. Je to most mezi fyzickým a digitálním světem.
{{< /img-text >}}