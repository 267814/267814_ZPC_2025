---
title: "2D Grafika & Design"
category: "Art & Design"
image: "/images/2d-main.jpg"
layout: "project"
date: 2024-01-02
---

{{< img-text title="Úvod" >}}
Tento modul se zaměřil na základy 2D počítačem podporovaného navrhování (CAD) a výroby (CAM). Byl rozdělen do dvou segmentů – řezání vinylu a řezání laserem – a hlavním cílem bylo ovládnout práci s vektorovou grafikou a osvojit si workflow potřebné pro převod digitálních náčrtů do fyzických objektů.
{{< /img-text >}}

{{< chapter title="01. Plotr" subtitle="Řezání vinylu & Samolepky" >}}

{{< img-text title="Koncept a skica" src="/images/prototyp-loga.jpg" size="tiny" >}}
Fáze vymýšlení začala analogovým skicováním na papír. Cílil jsem na klasický, opakovaně použitelný prvek značky, konkrétně monogram kombinující mé iniciály JH. Koncept spočíval v propletení písmen do jednoho sjednoceného symbolu, který by mohl sloužit jako osobní logo pro budoucí aplikace.
{{< /img-text >}}

{{< img-text title="Vektorizace v Inkscape" src="/images/proces-loga.jpg" reverse="true" >}}
Pro digitalizaci skici jsem importoval referenční fotografii do programu Inkscape (i když pro plynulejší workflow bych v budoucnu doporučil spíše Affinity Designer). Rastrový obrázek jsem překreslil (trace) a vytvořil tak editovatelné vektorové křivky. Během tohoto procesu jsem se mírně odklonil od původní skici a spojil 'J' a 'H' jedním plynulým tahem pro čistší a modernější estetiku. Výstup byl uložen jako SVG, což zajišťuje, že design závisí na matematických souřadnicích namísto pixelů a umožňuje nekonečnou škálovatelnost bez ztráty kvality.
{{< /img-text >}}

{{< img-text title="Finální produkt" >}}
Výroba zahrnovala vyřezání návrhu na vinylovém plotru s použitím samolepicího papíru. Zvolil jsem výrazný červený vinyl pro vysoký kontrast a výslednou samolepku aplikoval na nabíječku svého notebooku. Univerzálnost vektorového souboru mi umožnila logo využít napříč různými médii, včetně vizitek a především jako favicon tohoto webu.
{{< /img-text >}}

{{< gallery-row src1="/images/vyriznuty-logo.jpg" src2="/images/vuzite-logo.jpg" >}}


{{< chapter title="02. Laserová řezačka" subtitle="Prototypování z kartonu" >}}

{{< img-text title="Z 3D do 2D" >}}
Zadání vyžadovalo navrhnout stavebnici z kartonu spojovanou pouze třením (press-fit). Začal jsem modelováním vlastního vánočního stromku v 3D CAD prostředí. Sestava se skládala ze tří protínajících se částí stromu a základny. Modelování ve 3D bylo klíčové pro ověření tolerancí a zajištění správného lícování (interference fit) mezi komponenty před samotným řezáním materiálu.
{{< /img-text >}}

{{< 3d-model title="Koncept 3D sestavy" src="/models/tree.glb" >}}
Navrhnout to nejprve jako celek bylo zásadní pro kontrolu tolerancí.
{{< /3d-model >}}

<div class="grid grid-cols-1 md:grid-cols-2 gap-8 w-full">
    <div>
        {{< 3d-model title="Základna" src="/models/base.glb" >}}
        {{< /3d-model >}} 
    </div>
    <div>
        {{< 3d-model title="Díl stromku" src="/models/part.glb" >}}
        {{< /3d-model >}} 
    </div>
</div>


{{< img-text title="Export DXF souborů" >}}
Jakmile byla 3D geometrie hotová, promítl jsem plochy na 2D rovinu a exportoval je jako DXF soubory. Formát DXF slouží jako standard pro definování 2D drah nástroje (toolpaths) pro laserovou řezačku. Stejně jako SVG, i tyto soubory využívají vektorová data, což zajišťuje, že stroj sleduje přesné matematické křivky namísto pixelových aproximací.
{{< /img-text >}}

{{< gallery-row src1="/images/DXF-base.jpg" src2="/images/DXF-tree-parts.jpg" fit="contain" >}}


{{< img-text title="Proces a výsledek" >}}
Soubory jsem nahrál do ovládacího softwaru laseru a provedl tzv. nesting (skládání), abych optimalizoval využití kartonové desky. Práce stroje zahrnovala jak vektorové řezání pro obrys, tak rastrové gravírování pro text „Christmas 2025“ na základně. Finální sestava do sebe zapadla perfektně bez použití lepidla, což potvrdilo efektivitu digitálního prototypování v procesu navrhování.
{{< /img-text >}}

{{< media-row video="/images/Cut-proces.mp4" image="/images/cardboard-tree.jpg" >}}