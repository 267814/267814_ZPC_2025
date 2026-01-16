---
title: "AxisCore Gimbal" 
layout: "mainproject" 
date: 2025-02-15 
draft: false
subtitle: "3-Axis Camera Stabilization System"
---

{{< img-text title="Koncept & Vize" >}}
AxisCore vznikl jako ambiciózní experiment s cílem vytvořit plně funkční 3osý stabilizátor kamery pouze pomocí 3D tisku a dostupné elektroniky. Hlavní myšlenkou bylo dokázat, že i v domácích podmínkách lze dosáhnout profesionální úrovně stabilizace a designu. Celý systém je modulární, což umožňuje snadnou výměnu dílů a upgrady.
{{< /img-text >}}

{{< stats-counter >}}

{{< chapter title="Meet AxisCore" subtitle="The Complete System" >}}

{{< 3d-model-main title="Kompletní Sestava Gimbalu" src="models/full-assembly.glb" >}}
Plně funkční 3osý gimbal postavený z 3D tištěných dílů. Otočte model pro prozkoumání všech detailů. Všechny komponenty jsou navrženy pro maximální pevnost při minimální hmotnosti.
{{< /3d-model-main >}}

{{< tech-specs >}}

{{< chapter title="Design Journey" subtitle="From Sketch to Reality" >}}

<div class="grid grid-cols-1 md:grid-cols-3 gap-6 mb-24 w-full">

{{< interactive-card
title="Prvotní Návrh"
image="images/1st-prot.png"
full_image="images/1st-prot-sketch.jpg"
desc="Hledání ideálního tvaru."
full_desc="Hledání ideálního tvaru pro optimální rozložení váhy a ergonomii držadla. První skici byly velmi hrubé, ale definovaly základní 'L' tvar nosné konstrukce, který je typický pro jednoruční gimbally. Cílem bylo minimalizovat počet šroubových spojů a vytvořit co nejjednodušší mechaniku."
>}}

{{< interactive-card
title="Mechanika"
image="images/2nd-prot.png"
full_image="images/2nd-prot-sketch.jpg"
desc="Návrh převodového ústrojí."
full_desc="Detailní rozkreslení uložení střídavých motorů. Zde jsem řešil největší výzvu – jak přenést kroutící moment z motoru na rameno bez vůle. Nakonec jsem zvolil přímý náhon (direct drive) pro osy Pitch a Roll, a řemínkový převod pro osu Yaw. Každé ložisko je přesně umístěno pro minimální tření."
>}}

{{< interactive-card
title="Finální Design"
image="images/3rd-prot.png"
full_image="images/3rd-prot-sketch.jpg"
desc="Estetické ladění."
full_desc="Finální podoba AxisCore. Zahrnuje již integrovaný displej v rukojeti a joystick pro ovládání. Červené prvky nejsou jen dekorace, ale označují klíčové pohyblivé části a aretační mechanismy pro vyvážení kamery. Design byl několikrát iterován pro lepší ergonomii."
>}}

</div>

{{< chapter title="Component Breakdown" subtitle="Engineering Excellence" >}}

{{< component-3d 
title="Hlavní Tělo (Body Top)" 
src="models/body-top.glb"
image="images/body-top.jpg"
weight="145g"
material="PETG"
category="Structure"
>}}
Vrchní část hlavního rámu gimbalu. Tento díl nese největší mechanické zatížení a obsahuje montážní body pro všechny tři osy. **Konstrukce využívá topologické optimalizace** – materiál je pouze tam, kde je skutečně potřeba. 

Uvnitř je prostor pro **ESP32 řídící jednotku** a hlavní konektory. Díl je vytištěn z PETG pro optimální poměr pevnosti a hmotnosti. Důležité je přesné dodržení tolerancí ložisek – odchylka i 0.1mm způsobí vůli v mechanice.
{{< /component-3d >}}

{{< component-3d 
title="Spodní Kryt (Body Bottom)" 
src="models/body-bottom.glb"
image="images/body-bottom.jpg"
weight="98g"
material="PETG"
category="Structure"
reverse="true"
>}}
Spodní část těla slouží jako montážní bod pro rukojeť a zároveň jako kryt pro baterii a elektroniku. **Obsahuje integrované kabelové kanály** pro čisté vedení vodičů.

Speciální **ventilační otvory** zajišťují chlazení motorů při intenzivním použití. Díl je navržen pro snadný přístup k baterii – demontáž trvá jen pár sekund pomocí rychloupínacích šroubů.
{{< /component-3d >}}

{{< component-3d 
title="Rameno Y+X Osa" 
src="models/arm-Y+X-axis.glb"
image="images/arm-Y+X-axis.jpg"
weight="82g"
material="CF-Nylon"
category="Mechanical"
>}}
Kritická komponenta držící kameru. Musí být **extrémně tuhá, ale lehká** – každý gram navíc znamená vyšší zatížení motorů. Proto je vytištěna z **karbonového nylonu**, který má 3× vyšší pevnost než běžný PLA.

Rameno obsahuje **přesně vyfrézované drážky** pro rychloupínací systém kamery. Díky asymetrickému designu lze kameru vyvážit během několika sekund bez nástrojů.
{{< /component-3d >}}

{{< component-3d 
title="Rameno Z Osa" 
src="models/arm-Z-axis.glb"
image="images/arm-Z-axis.jpg"
weight="75g"
material="CF-Nylon"
category="Mechanical"
reverse="true"
>}}
Vertikální rameno je zodpovědné za stabilizaci v ose Yaw (otáčení). Design **minimalizuje moment setrvačnosti**, což umožňuje rychlejší reakci stabilizace.

Obsahuje **integrované vedení kabelů** pro připojení kamery. Díl je díky generativnímu designu optimalizován tak, aby vydržel zatížení až **5kg** při hmotnosti pouhých 75 gramů.
{{< /component-3d >}}

{{< component-3d 
title="Řídící PCB" 
src="models/PCB.glb"
image="images/PCB.jpg"
weight="35g"
material="FR4 + SMD"
category="Electronics"
>}}
Vlastní navržená deska plošných spojů s **ESP32 mikrokontrolerem**. Srdce celého systému. Řídí tři brushless motory pomocí pokročilého **PID regulátoru** s frekvencí 1000Hz.

Deska obsahuje **IMU senzor MPU6050** s 6 stupni volnosti (3-osý akcelerometr + 3-osý gyroskop), který měří pohyb s přesností 0.01°. Všechny komponenty jsou **SMD** pro minimální rozměry.
{{< /component-3d >}}

{{< component-3d 
title="Joystick" 
src="models/joystick.glb"
image="images/joystick.jpg"
weight="12g"
material="ABS"
category="Control"
reverse="true"
>}}
Analogový joystick pro manuální ovládání natočení kamery. Umožňuje **plynulé pohyby** na rozdíl od digitálních tlačítek. 

Použit je **Hall-effect senzor**, který nezná opotřebení mechanických kontaktů. Joystick je umístěn v ergonomickém místě, kde ho uchopí palec, aniž by operátor musel měnit úchop rukojeti.
{{< /component-3d >}}

{{< component-3d 
title="Phone Holder" 
src="models/phoneholder.glb"
image="images/phoneholder.jpg"
weight="45g"
material="TPU"
category="Accessory"
>}}
Elastický držák pro smartphone vytištěný z **TPU** (flexibilní filament). Umožňuje používat gimbal i s mobilním telefonem místo kamery.

Držák je univerzální – pojme telefony od 4.7" do 6.7" úhlopříčky. **Gumová výplň** chrání telefon před poškrábáním a zároveň zajišťuje pevný úchop i při rychlých pohybech.
{{< /component-3d >}}

{{< component-3d 
title="Hřídel (Shaft)" 
src="models/shaft-1.glb"
image="images/shaft-1.jpg"
weight="18g"
material="Ocel"
category="Mechanical"
reverse="true"
>}}
Přesně broušená ocelová hřídel pro uložení hlavní rotační osy. Není 3D tištěná – **CNC obrobená** z ušlechtilé oceli pro nulovou vůli.

Hřídel je osazena **kulkovými ložisky 608ZZ**, která zajišťují hladký a tichý chod. Tolerance výroby je **±0.01mm**, což je klíčové pro eliminaci vibrací při vysokých otáčkách stabilizace.
{{< /component-3d >}}

{{< component-3d 
title="Brushless Motor" 
src="models/motor-1.glb"
image="images/motor-1.jpg"
weight="55g"
material="Copper + NdFeB"
category="Electronics"
>}}
Každý motor má **14 pólů** a je schopen generovat dostatečný kroutící moment i při nízkých otáčkách. Použit je **direct drive** systém bez převodů pro eliminaci vůle.

Motory jsou řízeny pomocí **FOC (Field Oriented Control)** algoritmu, který umožňuje přesnou kontrolu momentu a pozice. Každý motor má vlastní **hall-effect senzory** pro detekci pozice rotoru s rozlišením 0.1°.
{{< /component-3d >}}

{{< chapter title="The Journey" subtitle="Behind the Scenes" >}}

{{< dev-journal >}}

{{< chapter title="What's Next?" subtitle="Future Upgrades" >}}

<div class="grid grid-cols-1 md:grid-cols-2 gap-6 mb-24">
<div class="bg-gradient-to-br from-[#2A2A2A] to-[#1a1a1a] border border-white/10 rounded-2xl p-8 hover:border-[#FF425C]/30 transition-all">
<h4 class="text-2xl font-bold text-white mb-4">🔋 Wireless Charging</h4>
<p class="text-gray-400">Implementace Qi bezdrátového nabíjení pro eliminaci USB portů a lepší odolnost proti vodě.</p>
</div>

<div class="bg-gradient-to-br from-[#2A2A2A] to-[#1a1a1a] border border-white/10 rounded-2xl p-8 hover:border-[#FF425C]/30 transition-all">
<h4 class="text-2xl font-bold text-white mb-4">📱 Bluetooth App</h4>
<p class="text-gray-400">Mobilní aplikace pro pokročilé nastavení PID parametrů a sledování telemetrie v reálném čase.</p>
</div>

<div class="bg-gradient-to-br from-[#2A2A2A] to-[#1a1a1a] border border-white/10 rounded-2xl p-8 hover:border-[#FF425C]/30 transition-all">
<h4 class="text-2xl font-bold text-white mb-4">🎯 Object Tracking</h4>
<p class="text-gray-400">AI-powered sledování objektů pomocí OpenCV a automatické zaostřování na cíl.</p>
</div>

<div class="bg-gradient-to-br from-[#2A2A2A] to-[#1a1a1a] border border-white/10 rounded-2xl p-8 hover:border-[#FF425C]/30 transition-all">
<h4 class="text-2xl font-bold text-white mb-4">⚡ Encoder Upgrade</h4>
<p class="text-gray-400">Přechod z Hall sensorů na magnetické enkodéry AS5600 pro 12-bit rozlišení pozice.</p>
</div>
</div>