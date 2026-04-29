# Základy Markdownu
Markdown je jednoduchý způsob formátování textu. Nepíšeš HTML tagy – používáš běžné znaky, které se automaticky zobrazí jako nadpisy, tučný text, seznam apod.

Nadpisy

# Hlavní nadpis (H1)
## Nadpis sekce (H2)
### Podnadpis (H3)

Pravidlo: V každém souboru používej # jen jednou – pro název stránky.

Tučný text a kurzíva

**tučný text**
*kurzíva*
***tučná kurzíva***

Seznamy

Odrážkový seznam (pořadí nezáleží):

- První bod
- Druhý bod
- Třetí bod
Číslovaný seznam (pořadí záleží):

1. Krok první
2. Krok druhý
3. Krok třetí
Vnořený seznam (odsaď dvěma mezerami):

- Hlavní bod
  - Podřazený bod
  - Další podřazený bod

Odkazy

[Text odkazu](https://adresa.cz)

Vložení obrázku

![Popis obrázku](/logo.png)

Kód – inline

Pro krátký kód v textu použij obrácené apostrofy:

Proměnnou deklarujeme pomocí `int cislo = 5;`


Kód – blok

Pro delší úseky kódu použij trojici obrácených apostrofů a uveď jazyk:

```python
def pozdrav(jmeno):
    print(f"Ahoj, {jmeno}!")
pozdrav("uživateli")
```
Místo python můžeš napsat csharp, html, css, javascript atd.

Citace / poznámky

> Toto je citace nebo důležitá poznámka.

Vodorovná čára (oddělovač)

---

Tabulka

| Sloupec 1 | Sloupec 2 | Sloupec 3 |
|-----------|-----------|-----------|
| hodnota A | hodnota B | hodnota C |
| hodnota D | hodnota E | hodnota F |
