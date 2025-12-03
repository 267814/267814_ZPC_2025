---
title: "3D Modelování & Tisk"
category: "Inženýrství"
image: "/images/featured/3D-model.png"
layout: "project"
date: 2024-01-03
---

{{< img-text title="Úvod" >}}
V tomto miniprojektu jsme se seznámili s 3D skenováním a modelováním. Ve skutečnosti většina z nás už věděla, jak vytvářet CAD modely, sestavy a co to 3D skenování obnáší. Byli však i studenti, pro které to byla novinka. Tento miniprojekt byl rozdělen do 4 úloh, ve kterých jsme si otestovali své znalosti a zkušenosti v SolidWorksu. Jako držitel 2 certifikátů (CSWA, CSWP) pro mě tyto úkoly nebyly tak náročné jako pro ostatní.
{{< /img-text >}}

{{< chapter title="01. CAD Modelování" subtitle="Návrh v SolidWorksu" >}}

{{< img-text title="Digitální rýsovací prkno" >}}
Tato sekce ukazuje práci, kterou jsem odvedl v CADu, což je v podstatě výchozí bod pro téměř každý projekt. K navrhování dílů jsem použil software **SolidWorks**. Než můžete cokoliv vyrobit nebo vytisknout, musíte to nejprve postavit v počítači. Mým cílem bylo zdokonalit se v softwaru navrhováním mnoha různých typů objektů. Procvičil jsem si tvorbu všeho od jednoduchých tvarů až po složitější sestavy s více díly, které do sebe zapadají.
{{< /img-text >}}

{{< 3d-model title="Pístnice" src="/models/piston.glb" >}}
Prvním úkolem bylo vytvořit pístnici. To byla nejjednodušší část ze všech, protože zahrnovala základní funkce v SolidWorksu. Ukázala, jak vytvořit skicu, co je to vysunutí atd.
{{< /3d-model >}}

{{< 3d-model title="Hřídel" src="/models/shaft.glb" >}}
Zde nebyl hlavním jádrem úkolu samotný model, ale výkres. Také velmi jednoduchý úkol, který vyžaduje nejen znalost fungování SolidWorksu, ale také norem a pravidel pro technické výkresy.
{{< /3d-model >}}

{{< img-text title="Technický výkres" >}}
Jak bylo řečeno dříve, pro vytvoření tohoto výkresu jsme potřebovali vědět, jak správně kreslit. Je to poměrně jednoduchý výkres, který se většina z nás učila už na střední škole. Jsou zde však věci, o kterých potřebujete technické znalosti (*například: Geometrické tolerance, lícování atd.*).

Co je na výkresu:
* Kóty
* Tolerance
* Geometrické tolerance
* Základny
* Řezy
* Drsnost povrchu
* Doplňující poznámky
{{< /img-text >}}

{{< media-row image="/images/hridel.jpg" >}}

{{< 3d-model title="Sestava kardanu" src="/models/cardan.glb" >}}
V tomto úkolu jsme dostali za úkol složit sestavu. V podstatě jde o páku spojenou s kloubem. Konkrétně je páka připojena ke kardanu, který pak otáčí hřídelí s pevnými stranami.
{{< /3d-model >}}

{{< 3d-model title="Držák" src="/models/holder.glb" >}}
Poté, co jsme dokončili jednodušší úkoly, přešli ti zkušenější na tyto 2 úlohy. Ty byly o dost těžší než ostatní, ale nakonec to bylo jen o troše přemýšlení a zkoušení.
{{< /3d-model >}}

{{< 3d-model title="Kryt" src="/models/cover.glb" >}}
Na druhou stranu kryt byl opravdu těžký. Rozhodně mi to zabralo déle, než jsem čekal. Zde jsme museli zapojit naši 3D představivost na jiné úrovni, protože poskytnutý výkres byl okótovaný tak málo, jak to jen šlo.
{{< /3d-model >}}


{{< chapter title="02. 3D Tisk" subtitle="Mechanický prototyp" >}}

{{< img-text title="Mechanická cedulka" >}}
Pro svůj projekt 3D tisku jsem se chtěl posunout za hranice statických modelů a vytvořit něco s funkčními, pohyblivými částmi. Rozhodl jsem se navrhnout a vyrobit mechanickou stavovou cedulku na stůl, která dokáže přepínat mezi **"FREE" (Volno)** a **"BUSY" (Obsazeno).** Tento projekt byl dokonalým testem navrhování pro montáž (DFA), kontroly tolerancí a tisku více do sebe zapadajících komponent.
{{< /img-text >}}

{{< img-text title="Pohled na rozložené díly" src="/images/Dissasambled.jpg" >}}
Zde jsou všechny jednotlivé komponenty, které tvoří finální sestavu, rozložené před složením. Navrhl jsem to jako vícedílný tisk s použitím kontrastních černých a bílých filamentů pro čistý vzhled.

Můžete vidět základnu, hlavní vertikální podpěry, velké ozubené kolo, menší pastorek, knoflíky a samozřejmě dvě cedulky "FREE" a "BUSY", které jsou navrženy tak, aby fungovaly jako ozubené hřebeny.
{{< /img-text >}}

{{< img-text title="Mechanismus" src="/images/Mechanism.jpg" reverse="true" size="portrait" >}}
Tento detailní záběr ukazuje jádro zařízení. Celý mechanismus se ovládá ručně otáčením malého knoflíku ve spodní části. Tento knoflík je připojen k malému pastorku.

Tento pastorek pohání větší ozubené kolo s **převodovým poměrem 2:1**, díky čemuž je pohyb plynulý a kontrolovaný. Tento rotační pohyb je pak převeden na lineární pohyb pomocí hřebenového mechanismu.
{{< /img-text >}}

{{< img-text title="Finální produkt v akci" >}}
A zde je finální, sestavený produkt ukazující své dva stavy. Když otočím knoflíkem, ozubený systém plynule zabere. Poměr 2:1 znamená, že otočení velkého kola o 180 stupňů prohodí nápisy.

Byl to naprostý úspěch a nyní mám na stole funkční, 3D vytištěnou vychytávku.
{{< /img-text >}}

{{< media-row video="/videos/3d_project_video.mp4" img_top="/images/Busy.jpg" img_bottom="/images/Free.jpg" >}}