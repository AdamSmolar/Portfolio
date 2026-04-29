# Teorie – Blok 2: Webová stránka (HTML, CSS, JavaScript)

## Co jsem se naučila

Pochopila jsem, proč se HTML, CSS a JavaScript drží odděleně v samostatných souborech – každý jazyk má jinou roli a míchání dohromady (inline styly, inline skripty) rychle vede k nepřehlednosti. Také jsem poprvé pracovala s DOM – bylo zajímavé, že JS může měnit obsah a vzhled stránky „za živa", bez obnovení stránky.

---

## Jak funguje prohlížeč

Prohlížeč stáhne HTML soubor, přečte ho a sestaví z něj stromovou strukturu – DOM (Document Object Model). Pak načte CSS a DOM vizuálně nastyluje. Nakonec spustí JavaScript, který s DOM může dál pracovat. Proto je důležité vkládat `<script>` s atributem `defer` – jinak se JS spustí dříve, než DOM existuje, a `querySelector` nic nenajde.

---

## CSS Custom Properties (proměnné)

Při dark mode jsem pochopila, k čemu jsou CSS proměnné. Definuji je jednou v `:root` a pak je používám všude:

```css
:root {
  --bg: #ffffff;
  --text: #111111;
}

body.dark {
  --bg: #1a1a1a;
  --text: #f0f0f0;
}

body {
  background-color: var(--bg);
  color: var(--text);
}
```

Když JavaScript přidá třídu `.dark` na `<body>`, přepíší se hodnoty proměnných a celá stránka se překreslí. Přijde mi to elegantnější než ručně měnit každý prvek zvlášť.

---

## Formuláře a validace

HTML formulář se dá odeslat i s prázdnými poli, pokud to nezablokuji. Naučila jsem se dvě úrovně validace:

1. **HTML validace** – atributy jako `required`, `type="email"` – prohlížeč zkontroluje sám
2. **JS validace** – vlastní logika před odesláním přes `event.preventDefault()`

```javascript
form.addEventListener('submit', (event) => {
  if (jmeno.value.trim() === '') {
    event.preventDefault(); // zastaví odeslání
    chyba.textContent = 'Vyplňte jméno.';
  }
});
```

---

## Slovník pojmů

---

**HTML (HyperText Markup Language)**
Jazyk pro popis struktury webové stránky. Říká, co na stránce je – nadpis, odstavec, obrázek, odkaz. Samotný HTML neurčuje, jak to vypadá.

---

**Tag**
Základní stavební prvek HTML. Skládá se z otevíracího tagu (`<p>`), obsahu a zavíracího tagu (`</p>`). Některé tagy jsou samouzavírací a obsah nemají: `<img />`, `<br />`.

---

**Sémantický tag**
Tag, jehož název vyjadřuje význam obsahu. Například `<header>` říká, že jde o záhlaví, `<nav>` o navigaci. Lepší než použít všude `<div>`, protože pomáhá čitelnosti kódu a vyhledávačům.

---

**CSS (Cascading Style Sheets)**
Jazyk pro definici vzhledu HTML prvků – barvy, rozměry, písma, rozložení. „Kaskádovitost" znamená, že pravidla se mohou dědit a přepisovat – přesnější pravidlo vždy vyhraje.

---

**Selektor**
Část CSS pravidla určující, na jaký element se styl aplikuje. `p` = všechny odstavce, `.trida` = prvky s danou třídou, `#id` = konkrétní prvek.

---

**Box model**
Každý HTML prvek v CSS zabírá obdélníkový prostor složený z: obsahu (content), vnitřního okraje (padding), rámečku (border) a vnějšího okraje (margin). Špatné pochopení box modelu bylo příčinou většiny mých chyb s rozměry.

---

**Flexbox**
CSS systém pro rozmístění prvků v jedné ose (řádek nebo sloupec). Pomocí `display: flex` na rodičovském prvku a vlastností jako `justify-content` a `align-items` se velmi snadno centruje a zarovnává obsah.

---

**CSS Grid**
Dvourozměrný layout systém – umožňuje rozmisťovat prvky do řádků i sloupců najednou. Použila jsem ho pro karty s alby.

---

**Media query**
Podmínka v CSS, která aplikuje styly jen při splnění určité podmínky – nejčastěji šířky obrazovky. Základ responzivního designu.

---

**DOM (Document Object Model)**
Stromová reprezentace HTML dokumentu, se kterou JavaScript pracuje. Každý tag je „uzel" stromu a JS ho může číst, měnit nebo mazat.

---

**Event listener**
Funkce, která „naslouchá" na určitou akci (klik, stisknutí klávesy, odeslání formuláře) a spustí se, když k ní dojde. Přidávám ho přes `addEventListener()`.

---

**`defer` atribut**
Atribut u `<script>` tagu, který říká prohlížeči: načti JS soubor, ale spusť ho až po zpracování celého HTML. Bez něj by JS běžel dřív, než DOM existuje.

---

**GitHub Pages**
Bezplatná služba GitHubu pro hostování statických webů přímo z repozitáře. Stačí zapnout v nastavení a stránka je dostupná na adrese `username.github.io/repo`.

---

## Zdroje

- [https://developer.mozilla.org/cs/](https://developer.mozilla.org/cs/) – kompletní reference
- [https://javascript.info/](https://javascript.info/) – výuka JS od základů, velmi přehledná
- [https://css-tricks.com/snippets/css/a-guide-to-flexbox/](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)
- [https://css-tricks.com/snippets/css/complete-guide-grid/](https://css-tricks.com/snippets/css/complete-guide-grid/)
