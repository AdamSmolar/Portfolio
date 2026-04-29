# Teorie – Blok 5: Vektorová grafika (Inkscape)

## Co jsem se naučil

Pochopil jsem zásadní rozdíl mezi vektorovou a rastrovou grafikou – nejen technicky, ale prakticky: logo, které potřebuji použít na tričku i na billboardu, musí být vektor. Rastr by byl rozmazaný. Naučil jsem se, že Inkscape soubor je vlastně textový XML soubor – SVG lze otevřít i v textovém editoru a upravit ručně.

---

## Vektorová vs. rastrová grafika

Rastrová grafika ukládá obraz jako mřížku pixelů. Při zvětšení se pixely zvětší a obraz „rozpixeluje". Vektorová grafika ukládá matematický popis objektů – při jakémkoli zvětšení se obraz přepočítá a zůstane ostrý.

Soubory SVG jsou textové (XML) – to znamená, že je lze editovat i v kódu, animovat přes CSS nebo zobrazit přímo v prohlížeči bez ztráty kvality.

---

## Bezierovy křivky

Bezierova křivka je definována kotevními body (anchors) a ovladači (handles). Handles určují směr a délku zakřivení v daném bodě. Jsou dvě:

- **Smooth node** – handles jsou souosé, přechod je plynulý
- **Cusp node** – handles jsou nezávislé, přechod je ostrý (roh)

Klíč k pochopení: handle netahám za bod samotný, ale za jeho ovladač – tím měním zakřivení.

---

## Boolean operace

Boolean operace kombinují dva a více překrývajících se objektů. Vyberu oba objekty (spodní = základ, horní = „nástroj") a operace vytvoří nový tvar:

- **Union** – sloučí do jednoho, vnější obrys obou tvarů
- **Difference** – odečte horní od spodního (výřez)
- **Intersection** – zachová jen překrývající část
- **Exclusion** – zachová části, které se nepřekrývají

Rozdíl oproti skupinování: Boolean operace je destruktivní – původní objekty zaniknou a vznikne nový tvar.

---

## Text na cestě

Funkce `Text → Put on Path` umístí text podél libovolné křivky nebo tvaru. Text sleduje tvar objektu – pro kruhové logo ideální. Tah (stroke) tvaru, podél kterého text jde, nastavím na „žádný" (None), aby byl neviditelný – slouží jen jako vodítko.

---

## Slovník pojmů

---

**Vektorová grafika**
Způsob ukládání grafiky jako matematického popisu objektů (body, křivky, tvary). Bezeztrátově škálovatelná – obraz je stejně ostrý v jakémkoli rozlišení.

---

**Rastrová grafika**
Způsob ukládání grafiky jako mřížky pixelů. Při zvětšení dochází ke ztrátě kvality (pixelace). Vhodná pro fotografie a komplexní obrazy.

---

**SVG (Scalable Vector Graphics)**
Otevřený formát pro vektorovou grafiku. Je to XML textový soubor – zobrazí se v prohlížeči, lze ho editovat kódem nebo Inkscapem. Standardní formát pro loga a ikony na webu.

---

**Path (cesta)**
Základní vektorový objekt – posloupnost uzlů spojených přímkami nebo křivkami. Všechny složité tvary jsou v SVG cesty.

---

**Anchor point (uzel)**
Bod definující tvar křivky. Každý uzel má polohu a volitelně handles (ovladače zakřivení).

---

**Handle (ovladač)**
Táhlo u uzlu křivky, které určuje směr a intenzitu zakřivení. Pohybem handle měním, jak křivka do uzlu přichází nebo z něj odchází.

---

**Bezierova křivka**
Matematická křivka definovaná kotevními body a handles. Pojmenovaná po francouzském inženýrovi Pierru Bézierovi, který ji použil pro design karosérií aut.

---

**Boolean operace**
Logická operace kombinující dva překrývající se objekty do nového tvaru. Základní typy: Union, Difference, Intersection, Exclusion.

---

**Fill (výplň)**
Vnitřní barva nebo vzor vektorového objektu. Může být plná barva, přechod (gradient) nebo vzor.

---

**Stroke (tah)**
Obrys vektorového objektu. Mám na výběr barvu, tloušťku a typ čáry (plná, přerušovaná, tečkovaná).

---

**Layer (vrstva)**
Logická vrstva v dokumentu umožňující organizaci objektů. Funguje jako průhledná fólie – objekty na vyšší vrstvě překrývají nižší.

---

**Gradient (přechod)**
Postupná změna barvy výplně z jedné barvy do druhé. Lineární přechod jde v přímce, radiální vychází ze středu.

---

**Kern / kerning**
Úprava prostoru mezi jednotlivými znaky textu pro vizuálně rovnoměrné rozmístění. Automatický kerning fontů je obvykle dostatečný, manuální potřebuji jen pro velká loga nebo nadpisy.

---

**Export PNG**
Převod SVG na rastrový obraz v požadovaném rozlišení. Pro tisk exportuji při 300 DPI, pro web při 96 DPI nebo v konkrétních pixelech.

---

**DPI (Dots Per Inch)**
Hustota bodů na palec. Vyšší DPI = více detailů na fyzické ploše. Pro tisk je minimem 300 DPI, pro web stačí 72–96 DPI (obrazovky mají fixní rozlišení).

---

## Zdroje

- [https://inkscape.org/learn/manual/](https://inkscape.org/learn/manual/)
- [https://practicaltypography.com/](https://practicaltypography.com/) – typografie, pomohlo mi s výběrem a sazbou fontu
- [https://developer.mozilla.org/en-US/docs/Web/SVG](https://developer.mozilla.org/en-US/docs/Web/SVG) – SVG reference, koukal jsem se, co SVG soubor obsahuje
