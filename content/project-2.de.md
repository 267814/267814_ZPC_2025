---
title: "2D-Grafik & Design"
category: "Art & Design"
image: "/images/2d-main.jpg"
layout: "project"
date: 2024-01-02
---

{{< img-text title="Einführung" >}}
Dieses Modul konzentrierte sich auf die Grundlagen des 2D Computer-Aided Design (CAD) und Computer-Aided Manufacturing (CAM). Unterteilt in zwei Segmente – Vinylschneiden und Laserschneiden – war das Hauptziel, Vektorgrafiken zu beherrschen und den Workflow zu verinnerlichen, der erforderlich ist, um digitale Skizzen in physische Objekte zu übersetzen.
{{< /img-text >}}

{{< chapter title="01. Der Plotter" subtitle="Vinylschnitt & Aufkleber" >}}

{{< img-text title="Das Konzept & Die Skizze" src="/images/prototyp-loga.jpg" size="tiny" >}}
Die Ideenfindungsphase begann mit analogem Skizzieren auf Papier. Ich strebte ein klassisches, wiederverwendbares Branding-Element an, konkret ein Monogramm, das meine Initialen JH kombiniert. Das Konzept sah vor, die Buchstaben ineinandergreifen zu lassen, um ein einheitliches Symbol zu schaffen, das als persönliches Logo für zukünftige Anwendungen dienen könnte.
{{< /img-text >}}

{{< img-text title="Vektorisierung in Inkscape" src="/images/proces-loga.jpg" reverse="true" >}}
Um die Skizze zu digitalisieren, importierte ich ein Referenzfoto in Inkscape (obwohl ich für einen reibungsloseren Workflow in Zukunft Affinity Designer empfehlen würde). Ich zeichnete das Rasterbild nach (Tracing), um bearbeitbare Vektorpfade zu erstellen. Während dieses Prozesses wich ich leicht von der ursprünglichen Skizze ab und verband das 'J' und 'H' mit einem einzigen durchgehenden Strich für eine sauberere, modernere Ästhetik. Die Ausgabe wurde als SVG gespeichert, wodurch sichergestellt wird, dass das Design auf mathematischen Koordinaten statt auf Pixeln basiert und eine unendliche Skalierbarkeit ohne Qualitätsverlust ermöglicht.
{{< /img-text >}}

{{< img-text title="Endprodukt" >}}
Die Fertigung umfasste das Schneiden des Designs auf einem Vinylplotter unter Verwendung von Klebefolie. Ich wählte ein leuchtend rotes Vinyl für hohen Kontrast und brachte den resultierenden Aufkleber auf meinem Laptop-Ladegerät an. Die Vielseitigkeit der Vektordatei ermöglichte es mir, das Logo über verschiedene Medien hinweg wiederzuverwenden, einschließlich Visitenkarten und vor allem als Favicon dieser Webseite.
{{< /img-text >}}

{{< gallery-row src1="/images/vyriznuty-logo.jpg" src2="/images/vuzite-logo.jpg" >}}


{{< chapter title="02. Laserschneider" subtitle="Prototyping mit Karton" >}}

{{< img-text title="Von 3D zu 2D" >}}
Die Aufgabe bestand darin, einen Press-Fit-Bausatz (Steckbausatz) aus Karton zu entwerfen. Ich begann mit der Modellierung eines individuellen Weihnachtsbaums in einer 3D-CAD-Umgebung. Die Baugruppe bestand aus drei sich kreuzenden Baumabschnitten und einer Basis. Die Modellierung in 3D war entscheidend für die Validierung der Toleranzen und die Sicherstellung einer korrekten Presspassung (Interference Fit) zwischen den Komponenten, bevor Material geschnitten wurde.
{{< /img-text >}}

{{< 3d-model title="3D-Baugruppenkonzept" src="/models/tree.glb" >}}
Es zuerst als komplettes Stück zu entwerfen, war entscheidend, um die Toleranzen zu prüfen.
{{< /3d-model >}}

<div class="grid grid-cols-1 md:grid-cols-2 gap-8 w-full">
    <div>
        {{< 3d-model title="Basisteil" src="/models/base.glb" >}}
        {{< /3d-model >}} 
    </div>
    <div>
        {{< 3d-model title="Baumteil" src="/models/part.glb" >}}
        {{< /3d-model >}} 
    </div>
</div>


{{< img-text title="Export von DXF-Dateien" >}}
Sobald die 3D-Geometrie fertiggestellt war, projizierte ich die Flächen auf eine 2D-Ebene und exportierte sie als DXF-Dateien. Das DXF-Format dient als Standard für die Definition von 2D-Werkzeugpfaden für den Laserschneider. Wie SVGs nutzen diese Dateien Vektordaten, wodurch sichergestellt wird, dass die Maschine präzisen mathematischen Kurven folgt, anstatt pixeligen Näherungen.
{{< /img-text >}}

{{< gallery-row src1="/images/DXF-base.jpg" src2="/images/DXF-tree-parts.jpg" fit="contain" >}}


{{< img-text title="Der Prozess & Das Ergebnis" >}}
Ich importierte die Dateien in die Steuerungssoftware des Laserschneiders und führte ein Nesting (Verschachtelung) durch, um den Materialverbrauch auf dem Kartonbogen zu optimieren. Der Maschinenbetrieb umfasste sowohl das Vektorschneiden für die Kontur als auch die Rastergravur für den Text „Christmas 2025“ auf der Basis. Die endgültige Baugruppe passte perfekt ohne Klebstoff zusammen, was die Effizienz des digitalen Prototypings im Designprozess bestätigte.
{{< /img-text >}}

{{< media-row video="/images/Cut-proces.mp4" image="/images/cardboard-tree.jpg" >}}