# Teorie – Blok 3: 3D grafika (Blender)

## Co jsem se naučil

Pochopil jsem základní rozdíl mezi 3D a 2D grafikou – ve 3D popisuji objekty matematicky v prostoru a výsledný obraz vzniká teprve renderováním. Naučil jsem se, že modelování a renderování jsou dvě oddělené fáze a každá vyžaduje jiné myšlení.

---

## Jak funguje 3D prostor v Blenderu

Blender používá tři osy: X (šířka), Y (hloubka), Z (výška). Každý objekt má svou polohu, rotaci a měřítko. Základní navigace: střední tlačítko myši pro rotaci pohledu, `Numpad 0` pro pohled z kamery, `G`/`R`/`S` pro pohyb/rotaci/scale objektu – a přidáním osy (`G Z`) omezím transformaci na jednu osu.

---

## Rozdíl mezi Object Mode a Edit Mode

V **Object Mode** pracuji s celými objekty – přesouvám je, kopíruji, přiřazuji materiály. V **Edit Mode** (`Tab`) upravuji samotnou geometrii – vrcholy, hrany, plochy. Je důležité si uvědomit, na které úrovni zrovna jsem, jinak operace dělají nečekané věci.

---

## Materiály a shader

Materiál určuje, jak povrch objektu vypadá. V Blenderu ho nastavuji v Shader Editoru pomocí uzlů (nodes). Základní materiál vždy obsahuje **Principled BSDF** – jeden shader s mnoha parametry:

- *Base Color* – základní barva nebo textura
- *Roughness* – 0 = zrcadlový lesk, 1 = matný povrch
- *Metallic* – kovový nebo nekovový charakter
- *Transmission* – průhlednost (pro sklo)

---

## Osvětlení a jeho vliv na scénu

Světlo v Blenderu neslouží jen k „rozsvícení" scény – definuje náladu, hloubku a realismus. Naučil jsem se, že jedno silné světlo tvoří tvrdé stíny (dramatické), více slabších zdrojů dává měkké stíny (přirozené). Barva světla ovlivňuje celkový dojem – teplé oranžové světlo (~3000 K) evokuje večer nebo interiér, studené modré (~6500 K) denní světlo nebo chlad.

---

## Slovník pojmů

---

**Mesh**
Datová struktura 3D objektu – soustava vrcholů, hran a ploch. Všechny objekty v Blenderu (krychle, koule, složitý model) jsou uvnitř meshe.

---

**Vertex (vrchol)**
Bod v 3D prostoru definovaný souřadnicemi X, Y, Z. Nejmenší stavební jednotka meshe. Z vrcholů se skládají hrany a z hran plochy.

---

**Edge (hrana)**
Úsečka spojující dva vrcholy. Tvoří „kostru" meshe.

---

**Face (plocha)**
Uzavřená smyčka hran tvořící polygon. Nejčastěji čtyřúhelník (quad). Plochy definují viditelný povrch objektu.

---

**Primitiv**
Předdefinovaný základní 3D tvar – krychle, koule, válec, kužel, torus. Slouží jako výchozí bod pro modelování složitějších objektů.

---

**Edit Mode**
Režim v Blenderu, kde upravuji geometrii objektu na úrovni vrcholů, hran a ploch. Přepínám do něj klávesou `Tab`.

---

**Boolean operace**
Logická operace kombinující dva objekty: Difference (výřez), Union (sjednocení), Intersection (průnik). Použil jsem Difference pro vytvoření otvoru okna ve stěně.

---

**Modifier**
Nedestruktivní úprava aplikovaná na objekt „nad" jeho geometrií. Lze ho kdykoli upravit nebo vypnout. Mirror modifier zdrcadlí objekt podle osy – modeluju jen jednu polovinu, druhá se vygeneruje automaticky.

---

**Materiál**
Definice vzhledu povrchu objektu – jak reaguje na světlo. V Blenderu se nastavuje přes Shader Editor pomocí uzlů.

---

**Principled BSDF**
Univerzální shader v Blenderu kombinující difuzní odrazy, lesk, průhlednost a další vlastnosti v jednom materiálu. BSDF = Bidirectional Scattering Distribution Function – popis toho, jak povrch rozptyluje světlo.

---

**Renderování**
Proces výpočtu výsledného 2D obrazu ze 3D scény. Výpočet zahrnuje osvětlení, stíny, odrazy a průhlednost.

---

**Cycles**
Fyzikálně korektní renderovací engine Blenderu založený na raytracingu. Pomalejší než EEVEE, ale realističtější výsledky – zejména odrazy a průhledné materiály.

---

**EEVEE**
Real-time renderovací engine Blenderu. Výrazně rychlejší než Cycles, ale aproximuje fyzikální chování světla. Vhodný pro stylizované výstupy nebo náhledy.

---

**Raytracing**
Metoda renderování simulující cestu světelných paprsků scénou – odraz od povrchů, lom v průhledných materiálech, stíny. Výpočetně náročná, ale fyzikálně přesná.

---

**HDRI (High Dynamic Range Image)**
Panoramatický obrázek použitý jako zdroj okolního osvětlení scény. Zajistí přirozené světelné podmínky bez nutnosti ručně přidávat světla.

---

**Outliner**
Panel v Blenderu zobrazující hierarchický seznam všech objektů ve scéně. Díky pojmenování objektů se v něm orientuji – bez pojmenování je vše „Cube.001", „Cube.002" atd.

---

## Zdroje

- [https://docs.blender.org/manual/en/latest/](https://docs.blender.org/manual/en/latest/)
- [https://polyhaven.com/](https://polyhaven.com/) – HDRI a textury (CC0 licence)
- [https://www.youtube.com/@blenderguru](https://www.youtube.com/@blenderguru)
