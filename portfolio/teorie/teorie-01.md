# Teorie – Blok 1: Konzolová aplikace (Python)

## Co jsem se naučil

V tomto bloku jsem poprvé psal větší program rozdělený do více souborů. Pochopil jsem, proč se kód dělí do funkcí a modulů – když jsem měl vše v jednom souboru, začalo být velmi těžké se v tom orientovat.

---

## Jak funguje struktura programu

Python program se spouští od shora dolů. Funkce se nejdřív definují (blok `def`), ale nespustí se, dokud je někdo nezavolá. Proto je zvykem mít na konci souboru podmínku:

```python
if __name__ == "__main__":
    main()
```

Tato podmínka zajistí, že `main()` se spustí jen při přímém spuštění souboru, ne při importu z jiného modulu. Přišlo mi to ze začátku divné, ale dává to smysl – modul může být jak spustitelný program, tak knihovna pro ostatní.

---

## Práce se soubory

Soubory se v Pythonu otevírají přes `open()`. Doporučený způsob je použít kontextový manažer `with`, který soubor automaticky zavře i při chybě:

```python
with open("data.txt", "r", encoding="utf-8") as f:
    obsah = f.readlines()
```

Módy otevření: `"r"` = čtení, `"w"` = zápis (přepíše), `"a"` = přidání na konec. Vždy uvádím `encoding="utf-8"`, jinak mohou nastat problémy s diakritikou.

---

## Výjimky

Výjimka je chyba, která nastane za běhu programu. Python ji „vyhodí" a pokud ji nezachytíme, program spadne. Pomocí `try/except` ji zachytíme a reagujeme:

```python
try:
    hodnota = int(input("Zadej číslo: "))
except ValueError:
    print("To není číslo.")
```

Naučil jsem se, že je lepší zachytávat konkrétní typy výjimek (`ValueError`, `FileNotFoundError`) než obecné `except Exception`, protože obecné zachytí i chyby, které bychom raději viděli.

---

## Moduly a import

Když jsem rozdělil kód do dvou souborů, musel jsem se naučit import. V `main.py` stačí napsat:

```python
import uloziste
uloziste.uloz_zaznam(data)
```

nebo

```python
from uloziste import uloz_zaznam
uloz_zaznam(data)
```

Druhý způsob je kratší, ale při více importech z různých modulů může být matoucí, odkud funkce pochází.

---

## Slovník pojmů

Pojmy, které jsem se naučil během tohoto bloku a vlastními slovy vysvětlím, co znamenají.

---

**Algoritmus**
Přesný postup řešení nějakého problému. Musí mít jasný začátek, konec a každý krok musí být jednoznačný. Například postup pro výpočet průměru: sečti čísla, vyděl počtem prvků.

---

**Funkce**
Pojmenovaný blok kódu, který dělá jednu konkrétní věc. Zavolám ji jménem a může mi vrátit výsledek přes `return`. Funkce jsem použil proto, abych stejný kód nemusel psát vícekrát.

---

**Parametr**
Vstup funkce – proměnná, kterou funkci předám při volání. Funkce `vypocitej_soucet(cisla)` má parametr `cisla`. Rozdíl oproti běžné proměnné je v tom, že parametr existuje jen uvnitř funkce.

---

**Návratová hodnota**
To, co funkce vrátí přes `return`. Nemusí to být číslo – může to být seznam, slovník nebo `None` (nic). Pokud funkce nemá `return`, vrací automaticky `None`.

---

**List (seznam)**
Datová struktura pro ukládání více hodnot za sebou. Píše se do hranatých závorek: `[1, 2, 3]`. Prvky mohou být různého typu. Přistupuji k nim přes index začínající od nuly: `seznam[0]` je první prvek.

---

**Dictionary (slovník)**
Datová struktura ukládající páry klíč–hodnota. Píše se do složených závorek: `{"jmeno": "Kamil", "vek": 17}`. Na rozdíl od listu nepřistupuji přes číselný index, ale přes klíč: `zaznam["jmeno"]`.

---

**Výjimka (Exception)**
Chyba, která nastane za běhu programu – například dělení nulou nebo zadání textu místo čísla. Pokud ji nezachytím, program spadne s chybovou hláškou. Zachytávám ji přes `try/except`.

---

**Modul**
Soubor s Pythonem kódem (`.py`), který obsahuje funkce nebo proměnné určené pro použití jinde. Importuji ho přes `import nazev_modulu`. Výhoda je, že logicky oddělím části programu do samostatných souborů.

---

**Git**
Nástroj pro verzování kódu – sleduje historii změn v souborech. Každá uložená verze se nazývá commit. Díky Gitu jsem se mohl vrátit k předchozí funkční verzi, když jsem něco pokazil.

---

**Commit**
Jeden „snímek" stavu projektu uložený v Gitu. Každý commit má zprávu popisující, co se změnilo. Správná zpráva říká co a proč, ne jen „oprava" nebo „update".

---

**GitHub**
Webová platforma pro ukládání a sdílení Git repozitářů. Umožňuje přistupovat ke kódu odkudkoli a sdílet ho s ostatními.

---

## Zdroje

- [https://docs.python.org/3/tutorial/errors.html](https://docs.python.org/3/tutorial/errors.html) – výjimky v Pythonu
- [https://docs.python.org/3/tutorial/inputoutput.html](https://docs.python.org/3/tutorial/inputoutput.html) – práce se soubory
- [https://git-scm.com/doc](https://git-scm.com/doc) – Git dokumentace
