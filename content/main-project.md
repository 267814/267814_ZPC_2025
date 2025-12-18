---
title: "AxisCore Gimbal"
layout: "mainproject"
date: 2025-02-15
draft: false
---

{{< img-text title="Koncept & Vize" >}}
AxisCore vznikl jako ambiciózní experiment s cílem vytvořit plně funkční 3osý stabilizátor kamery pouze pomocí 3D tisku a dostupné elektroniky. Hlavní myšlenkou bylo dokázat, že i v domácích podmínkách lze dosáhnout profesionální úrovně stabilizace a designu. Celý systém je modulární, což umožňuje snadnou výměnu dílů a upgrady.
{{< /img-text >}}

{{< chapter title="01. Prototyping" subtitle="Sketches & Ideas" >}}

<!-- SKETCHES GRID - 3 KARTY VEDLE SEBE -->

<div class="grid grid-cols-1 md:grid-cols-3 gap-6 mb-24 w-full">
<div class="project-card md:col-span-1 flex flex-col h-full cursor-pointer group relative min-h-[350px]" @click="modalOpen = true; activeSketch = { src: '/images/sketch-main.jpg', title: 'Prvotní Návrh', desc: 'Hledání ideálního tvaru pro optimální rozložení váhy a ergonomii držadla. První skici byly velmi hrubé, ale definovaly základní L tvar nosné konstrukce, který je typický pro jednoruční gimbally. Cílem bylo minimalizovat počet šroubových spojů.' }"><div class="absolute inset-0"><img src="/images/sketch-main.jpg" class="w-full h-full object-cover group-hover:scale-105 transition duration-700 opacity-60 group-hover:opacity-100"><div class="absolute inset-0 bg-gradient-to-t from-black via-black/50 to-transparent"></div></div><div class="absolute bottom-0 left-0 p-8 w-full"><h3 class="text-2xl font-bold text-white mb-2 group-hover:text-[#FF425C] transition">Prvotní Návrh</h3><p class="text-gray-300 text-sm">Hledání ideálního tvaru.</p><div class="mt-4 text-xs font-bold uppercase tracking-widest text-[#FF425C] opacity-0 transform translate-y-4 group-hover:translate-y-0 group-hover:opacity-100 transition duration-300">Rozkliknout ↗</div></div></div>
<div class="project-card md:col-span-1 flex flex-col h-full cursor-pointer group relative min-h-[350px]" @click="modalOpen = true; activeSketch = { src: '/images/sketch-side.jpg', title: 'Mechanika', desc: 'Detailní rozkreslení uložení střídavých motorů. Zde jsem řešil největší výzvu – jak přenést kroutící moment z motoru na rameno bez vůle. Nakonec jsem zvolil přímý náhon (direct drive) pro osy Pitch a Roll, a řemínkový převod pro osu Yaw.' }"><div class="absolute inset-0"><img src="/images/sketch-side.jpg" class="w-full h-full object-cover group-hover:scale-105 transition duration-700 opacity-60 group-hover:opacity-100"><div class="absolute inset-0 bg-gradient-to-t from-black via-black/50 to-transparent"></div></div><div class="absolute bottom-0 left-0 p-8 w-full"><h3 class="text-2xl font-bold text-white mb-2 group-hover:text-[#FF425C] transition">Mechanika</h3><p class="text-gray-300 text-sm">Návrh převodového ústrojí.</p><div class="mt-4 text-xs font-bold uppercase tracking-widest text-[#FF425C] opacity-0 transform translate-y-4 group-hover:translate-y-0 group-hover:opacity-100 transition duration-300">Rozkliknout ↗</div></div></div>
<div class="project-card md:col-span-1 flex flex-col h-full cursor-pointer group relative min-h-[350px]" @click="modalOpen = true; activeSketch = { src: '/images/sketch-detail.jpg', title: 'Finální Design', desc: 'Finální podoba AxisCore. Zahrnuje již integrovaný displej v rukojeti a joystick pro ovládání. Červené prvky nejsou jen dekorace, ale označují klíčové pohyblivé části a aretační mechanismy pro vyvážení kamery.' }"><div class="absolute inset-0"><img src="/images/sketch-detail.jpg" class="w-full h-full object-cover group-hover:scale-105 transition duration-700 opacity-60 group-hover:opacity-100 object-center"><div class="absolute inset-0 bg-gradient-to-t from-black via-black/50 to-transparent"></div></div><div class="absolute bottom-0 left-0 p-8 w-full"><h3 class="text-2xl font-bold text-white mb-2 group-hover:text-[#FF425C] transition">Finální Design</h3><p class="text-gray-300 text-sm">Estetické ladění.</p><div class="mt-4 text-xs font-bold uppercase tracking-widest text-[#FF425C] opacity-0 transform translate-y-4 group-hover:translate-y-0 group-hover:opacity-100 transition duration-300">Rozkliknout ↗</div></div></div>
</div>

{{< 3d-model title="Kompletní sestava" src="/models/full-assembly.glb" >}}
Kompletní sestava AxisCore v plné kráse. Zde můžete vidět, jak do sebe všechny díly zapadají.
{{< /3d-model >}}

{{< chapter title="02. Komponenty" subtitle="Detailní popis dílů" >}}

{{< img-text title="Hlavní Rám (Body)" src="/images/part-body.jpg" >}}
Centrální nosný prvek celého gimbalu. Je navržen tak, aby odolával torzním silám při rychlých pohybech. Uvnitř se nachází řídící jednotka ESP32 a baterie.

Dev Note: Tip: Tiskni s 4 perimetry a 40% gyroid výplní pro maximální tuhost. Orientace tisku je klíčová pro pevnost vrstev.
{{< /img-text >}}

{{< 3d-model src="/models/body.glb" title="3D Model: Body" >}}
{{< /3d-model >}}

{{< img-text title="Rameno (Arm Pitch)" src="/images/part-arm.jpg" reverse="true" >}}
Rameno držící samotnou kameru. Musí být co nejlehčí, aby nezatěžovalo motory, ale zároveň pevné, aby nedocházelo k vibracím.

Dev Note: Použil jsem topologickou optimalizaci ve Fusion 360 k odstranění přebytečného materiálu. Ušetřeno 35g váhy.
{{< /img-text >}}

{{< 3d-model src="/models/arm.glb" title="3D Model: Arm" >}}
{{< /3d-model >}}

{{< img-text title="Rukojeť (Handle)" src="/images/part-handle.jpg" >}}
Ergonomicky tvarovaná rukojeť s protiskluzovou texturou. Obsahuje slot pro baterii 18650 a joystick pro ovládání náklonu.

Dev Note: Textura byla generována procedurálně v Blenderu a poté aplikována na model. Tisk z TPU by byl ideální pro lepší grip.
{{< /img-text >}}

{{< 3d-model src="/models/handle.glb" title="3D Model: Handle" >}}
{{< /3d-model >}}

{{< chapter title="03. Timeline" subtitle="Development Progress" >}}

<div class="grid grid-cols-1 md:grid-cols-4 gap-6 mt-12 mb-24 w-full">
<div class="bg-[#222] p-6 rounded-2xl border border-white/5 relative">
<div class="absolute -top-4 -left-4 w-12 h-12 bg-[#FF425C] rounded-full flex items-center justify-center font-bold text-white text-sm shadow-lg">Q1</div>
<h4 class="text-xl font-bold text-white mt-4 mb-2">Výzkum & Návrh</h4>
<p class="text-gray-400 text-sm">Analýza existujících řešení, výběr motorů a první CAD náčrty ve Fusion 360.</p>
</div>

<div class="bg-[#222] p-6 rounded-2xl border border-white/5 relative">
    <div class="absolute -top-4 -left-4 w-12 h-12 bg-[#2A2A2A] border-2 border-[#FF425C] rounded-full flex items-center justify-center font-bold text-white text-sm shadow-lg">Q2</div>
    <h4 class="text-xl font-bold text-white mt-4 mb-2">Prototypování</h4>
    <p class="text-gray-400 text-sm">Tisk prvních verzí ramen. Testování tuhosti materiálů PLA vs PETG vs CF-Nylon.</p>
</div>

<div class="bg-[#222] p-6 rounded-2xl border border-white/5 relative">
    <div class="absolute -top-4 -left-4 w-12 h-12 bg-[#2A2A2A] border-2 border-[#FF425C] rounded-full flex items-center justify-center font-bold text-white text-sm shadow-lg">Q3</div>
    <h4 class="text-xl font-bold text-white mt-4 mb-2">Elektronika</h4>
    <p class="text-gray-400 text-sm">Programování PID regulátoru pro ESP32. První úspěšná stabilizace v jedné ose.</p>
</div>

<div class="bg-[#222] p-6 rounded-2xl border border-white/5 relative">
    <div class="absolute -top-4 -left-4 w-12 h-12 bg-[#2A2A2A] border-2 border-[#FF425C] rounded-full flex items-center justify-center font-bold text-white text-sm shadow-lg">Q4</div>
    <h4 class="text-xl font-bold text-white mt-4 mb-2">Finalizace</h4>
    <p class="text-gray-400 text-sm">Kompletní montáž, cable management, lakování a finální kalibrace softwaru.</p>
</div>


</div>