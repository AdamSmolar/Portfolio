# Teorie – Blok 7: Střih videa (DaVinci Resolve)

## Co jsem se naučil

Pochopil jsem, že střih videa není jen „dávání záběrů za sebou" – výběr, délka a pořadí záběrů vytváří emoce a vyprávění. Naučil jsem se, že zvuk je stejně důležitý jako obraz, a že špatný zvuk diváka odradí rychleji než špatný záběr.

---

## Jak funguje video

Video je sekvence statických snímků (frames) přehrávaných dostatečně rychle – mozek je vnímá jako plynulý pohyb. Standardní frekvence je 25 fps (evropský broadcast standard PAL). Každý snímek je obrázek v určitém rozlišení.

Výsledný soubor je komprimován kodekem – algoritmem, který odstraní redundantní informace. H.264 (MP4) je nejpoužívanější – dobrý poměr kvality a velikosti souboru.

---

## Workflow v DaVinci Resolve

DaVinci Resolve je organizován do stránek – každá slouží jinému účelu:

1. **Media** – importuji záběry, organizuji do Binů (složek)
2. **Cut / Edit** – skládám timeline, střihám záběry, přidávám titulky
3. **Fairlight** – upravuji zvuk (hlasitost, šum, equalizer)
4. **Color** – korigruji barvy a expozici záběrů
5. **Deliver** – nastavuji export a generuji výsledný soubor

Důležité: timeline je nedestruktivní – originální soubory zůstávají nedotčené. Vše, co dělám v timeline, jsou jen instrukce, jak záběry poskládat a upravit.

---

## Střih a rytmus

Střih není náhodný. Záběry střídám tak, aby udržely tempo a zájem diváka. Při rytmickém střihu na hudbu markiruji beaty v audio stopě a střihy záměrně pokládám na přechody. Výsledek působí dynamicky i bez složitých efektů.

Základní pravidlo: záběr drží divákovi pozornost přibližně 3–7 sekund. Kratší = dynamické, rychlé. Delší = klidné, meditativní – ale hrozí ztráta pozornosti.

---

## Zvuk

Zvuk v post-produkci má dvě vrstvy:

- **Diegetický zvuk** – zvuk ze scény (hlasy, kroky, okolí). Upravuji hlasitost tak, aby byl přirozený, ne příliš hlasitý.
- **Nediegetický zvuk** – přidaná hudba nebo komentář. Hudbě typicky snížím hlasitost na −20 dB, aby nepřekrývala dialogy.

Noise Reduction ve Fairlight odstraní konstantní šum (bzučení, šum klimatizace) – funguje tak, že analyzuji tiché místo záznamu jako „profil šumu" a pak ho odečtu od celé stopy.

---

## Slovník pojmů

---

**Frame (snímek)**
Jeden statický obraz ve videu. Video je sekvence framů přehrávaných rychle za sebou.

---

**FPS (Frames Per Second)**
Počet snímků za sekundu. 24 fps = filmový standard. 25 fps = evropský broadcast (PAL). Vyšší FPS = plynulejší pohyb.

---

**Rozlišení**
Počet pixelů v obrazu. HD = 1280×720, Full HD = 1920×1080, 4K = 3840×2160. Vyšší rozlišení = více detailů, větší soubory.

---

**Codec**
Algoritmus komprimující video soubor. H.264 je nejpoužívanější – dobrý poměr kvality a velikosti. H.265 je modernější a efektivnější, ale náročnější na výkon.

---

**Timeline**
Časová osa v střihovém programu. Na stopách leží videoklipy a zvukové záznamy seřazené v čase.

---

**Clip**
Jeden nahraný záběr – zdrojový soubor z kamery nebo telefonu.

---

**Bin**
Složka v DaVinci Resolve pro organizaci importovaných záběrů. Pomáhá udržet projekt přehledný, zvláště při více dnech natáčení.

---

**Cut**
Základní střih – přímé navázání jednoho záběru na druhý bez přechodu. Nejčastěji používaný střih.

---

**Dissolve (prolínačka)**
Přechod mezi záběry, kde jeden plynule přechází do druhého. Evokuje plynutí času nebo změnu místa.

---

**Transition (přechod)**
Vizuální efekt při střihu. Přechody mají dramaturgický důvod – nepoužívám je jen proto, aby to „vypadalo zajímavě".

---

**B-roll**
Doplňkové záběry bez hlavního subjektu, vkládané pro ilustraci. V dokumentu jsou B-rollem záběry prostředí, detaily, ruky pracující atd.

---

**Diegetický zvuk**
Zvuk pocházející ze scény, který by postavy ve scéně slyšely (hlasy, kroky, hluk prostředí).

---

**Nediegetický zvuk**
Zvuk přidaný v postprodukci, který postavy ve scéně neslyší (hudba na pozadí, komentář).

---

**Noise Reduction**
Funkce v audio editoru odstraňující konstantní šum záznamu (bzučení, šum mikrofonu). Analyzuji profil šumu z tichého místa a odečtu ho od celé stopy.

---

**G-code (Deliver)**
V kontextu DaVinci – Deliver page generuje výsledný video soubor z timeline podle zvoleného nastavení (rozlišení, kodek, bitrate).

---

**H.264**
Nejpoužívanější video kodek. Ukládá video jako MP4 soubor s dobrou kvalitou a přiměřenou velikostí. Podporují ho všechny platformy a zařízení.

---

**Bitrate**
Datový tok videa – kolik dat se přenáší za sekundu (Mbps). Vyšší bitrate = lepší kvalita, větší soubor.

---

**Color grading**
Umělecká úprava barev záběrů pro vytvoření konzistentní vizuální nálady. Liší se od color correction, kde jen opravuji technické chyby (špatná expozice, vyvážení bílé).

---

## Zdroje

- [https://www.blackmagicdesign.com/products/davinciresolve/training](https://www.blackmagicdesign.com/products/davinciresolve/training)
- [https://www.youtube.com/@CaseyFaris](https://www.youtube.com/@CaseyFaris)
- Murch, Walter: *In the Blink of an Eye* – přečetl jsem výňatky online, zajímavý pohled na filozofii střihu
- [https://nofilmschool.com/](https://nofilmschool.com/) – články o technice natáčení
