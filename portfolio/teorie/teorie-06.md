# Teorie – Blok 6: 3D tisk

## Co jsem se naučila

Pochopila jsem, že 3D tisk není jen „stisknu tlačítko a vytiskne se model" – příprava v sliceru a správné nastavení parametrů trvá déle než samotný tisk. Naučila jsem se uvažovat o modelu z pohledu tiskárny: jak leží na podložce, kde jsou přesahy a jak silné mají být stěny.

---

## Jak FDM tisk funguje

Tiskárna taví filament v tiskové hlavě (hotend, tryska) a nanáší ho na tiskovou podložku. Každá vrstva se ochladí a slepí s předchozí. Tisk začíná vždy od spodní vrstvy a jde nahoru.

Klíčový je první vrstva – musí dobře přilnout k podložce. Pokud je tryska příliš vysoko, vlákno nesedí. Příliš nízko a ucpe trysku. Správná výška první vrstvy (Live Adjust Z) je asi polovina průměru trysky.

---

## Co je slicer a co dělá

Slicer je software, který převede 3D model (STL, 3MF) na G-code – textový soubor s instrukcemi pohybu, teplot a podavače. Bez sliceru tiskárna model nečte. Slicer rozdělí model na vrstvy (slices – odtud název) a vygeneruje dráhy pro každou vrstvu.

---

## Infill – výplň

Infill je vnitřní vzor, který slicer generuje uvnitř plného tělesa. Není nutné tisknout objekt plný – plast uvnitř je těžký, pomalý a drahý. Výplň 15–20 % je dostatečná pro většinu dekorativních objektů. Funkční díly vyžadují 40+ %.

Vzory výplně ovlivňují pevnost a pružnost: Gyroid je oblíbený pro rovnoměrné vlastnosti ve všech směrech, honeycomb je pevný v tlaku, grid je nejrychlejší.

---

## Supports a overhangs

Tiskárna nanáší plast na předchozí vrstvu – pokud pod ní nic není (overhang), plast visí ve vzduchu a deformuje se. Pravidlo 45°: přesahy do 45° tiskárna zvládne bez supports. Strmější vyžadují podpůrné struktury (supports), které se po tisku odlomí.

Supports jsou nevyhnutelné, ale zanechávají stopy na povrchu. Proto je vhodné co nejdříve orientovat model tak, aby přesahů bylo co nejméně.

---

## Slovník pojmů

---

**3D tisk (aditivní výroba)**
Proces vytváření fyzického objektu z digitálního modelu postupným nanášením materiálu vrstvu po vrstvě. Opak frézování (subtraktivní výroby), kde se materiál odebírá.

---

**FDM (Fused Deposition Modeling)**
Nejrozšířenější metoda 3D tisku – tavení plastového filamentu a jeho nanášení přes trysku. Výsledek má viditelné vrstvy.

---

**Filament**
Plastové vlákno navinuté na cívce, které tiskárna taví a nanáší. Nejčastější materiály: PLA, PETG, ABS.

---

**PLA (Polylactic Acid)**
Nejpoužívanější materiál pro FDM tisk. Snadno se tiskne, minimální deformace, biologicky odbouratelný. Nevhodný pro části vystavené teplotám nad ~60 °C.

---

**STL**
Formát souboru popisující povrch 3D modelu jako soustavu trojúhelníků. Nejrozšířenější formát pro 3D tisk. Neobsahuje informace o barvě nebo materiálu.

---

**3MF**
Modernější formát 3D tisku obsahující geometrii, barvy, materiál a tisková nastavení v jednom souboru. Postupně nahrazuje STL.

---

**Slicer**
Software převádějící 3D model (STL/3MF) na G-code. Rozdělí model na vrstvy a vygeneruje dráhy pohybu tiskové hlavy. Příklady: PrusaSlicer, Cura.

---

**G-code**
Textový soubor s instrukcemi pro tiskárnu – souřadnice pohybů, teploty, rychlosti, podávání filamentu. Generuje ho slicer automaticky.

---

**Layer height (výška vrstvy)**
Tloušťka jedné tištěné vrstvy v mm. Nižší = jemnější povrch a delší tisk. Vyšší = hrubší povrch a kratší tisk. Typicky 0,1–0,3 mm.

---

**Infill (výplň)**
Vnitřní vzor generovaný slicerem uvnitř plného tělesa. Vyjadřuje se v procentech: 0 % = dutý, 100 % = plný. Vzor i hustota ovlivňují pevnost a hmotnost.

---

**Perimetr**
Vnější obrysová linka tisknutá kolem každé vrstvy. Více perimetrů = pevnější stěny. Typicky 2–3 perimetry.

---

**Support (podpora)**
Podpůrná struktura generovaná slicerem pod přesahy modelu. Po tisku se mechanicky odstraní. Zanechává stopy na povrchu.

---

**Overhang (přesah)**
Část modelu vyčnívající do vzduchu bez podkladu. Tiskárna zvládá přesahy přibližně do 45° bez supports.

---

**Warping**
Deformace tisku způsobená nerovnoměrným chladnutím – rohy a okraje se odlepují od podložky. Řeším Brimem nebo vyšší teplotou podložky.

---

**Brim**
Plochý „lem" kolem první vrstvy modelu generovaný slicerem. Zvyšuje kontaktní plochu s podložkou a zabraňuje warpingu. Odlomí se po tisku.

---

**Raft**
Silnější plošina pod celým modelem. Lepší adheze než Brim, ale obtížnější odstranění. Vhodný pro malé nebo nestabilní objekty.

---

**Hotend / tryska (nozzle)**
Část tiskové hlavy, kde se filament taví a vytlačuje. Standardní průměr trysky je 0,4 mm. Menší = jemnější detail, pomalejší. Větší = rychlejší, hrubší.

---

## Zdroje

- [https://help.prusa3d.com/cs/](https://help.prusa3d.com/cs/)
- [https://www.printables.com/](https://www.printables.com/)
- [https://all3dp.com/](https://all3dp.com/) – články o materiálech a parametrech tisku
