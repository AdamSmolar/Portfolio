# Blok 1 – Konzolová aplikace (Python)

## Cíl

Chtěl jsem vytvořit aplikaci, která mi pomůže sledovat, kolik jsem ten den vypil vody. Aplikace se ptá na počet sklenic, zapisuje záznamy do souboru a na konci ukáže celkový příjem a zhodnotí, jestli jsem splnil doporučený denní limit.

---

## Postup

Nejdřív jsem si nakreslil na papír, co aplikace má umět – přidat záznam, zobrazit historii a vymazat dnešní data. Pak jsem začal programovat postupně: nejdřív funkci pro přidávání záznamu, pak čtení ze souboru a nakonec výpočet součtu.

Největší problém byl, když jsem zapomněl ošetřit případ, že soubor ještě neexistuje – program padal s `FileNotFoundError`. Vyřešil jsem to přes `try/except` a výchozí prázdný seznam.

Průběžně jsem commitoval na GitHub s popisnými zprávami, abych se mohl vrátit k předchozí verzi, když jsem něco pokazil.

---

## Výstupy

- Soubory `main.py` a `uloziste.py` na GitHubu
- Data se ukládají do `data/zaznamy.txt`
- Ukázka výstupu aplikace:

```
=== Sledování pitného režimu ===
1) Přidat záznam
2) Zobrazit historii
3) Konec

Volba: 1
Počet sklenic: 3
Uloženo. Celkem dnes: 3 sklenice (0.75 l)

Volba: 2
--- Historie ---
14:32  3 sklenice
15:48  2 sklenice
Celkem: 5 sklenic (1.25 l) — doporučeno: 8 sklenic (2 l)
```

---

## Reflexe

Aplikace funguje tak, jak jsem plánoval. Překvapilo mě, jak moc práce je jen ošetření špatných vstupů – myslel jsem, že to bude triviální, ale uživatel může zadat cokoli. Příště bych rovnou psal funkce kratší a více oddělené, protože funkce `zobraz_historii()` mi nakonec dělala víc věcí najednou a bylo těžší ji ladit. Verzování přes Git mi skutečně pomohlo – jednou jsem se vrátil o dva commity zpět, protože jsem rozbil načítání souboru.

---

## Teoretické pozadí (stručně)

V projektu jsem pracoval s funkcemi, výjimkami (`try/except`) a se soubory. Datové struktury jsem použil hlavně seznam (list) pro historii záznamů a slovník (dict) pro jeden záznam s časem a hodnotou. Kód je rozdělený do dvou modulů – `main.py` řídí tok programu, `uloziste.py` se stará o čtení a zápis dat. Verzování jsem dělal přes Git a repozitář je na GitHubu.

Podrobnější vysvětlení pojmů je v souboru `teorie.md`.

---

## Zdroje

- [https://docs.python.org/3/](https://docs.python.org/3/) – dokumentace Pythonu, hlavně sekce o souborech a výjimkách
- [https://realpython.com/python-exceptions/](https://realpython.com/python-exceptions/) – článek o ošetření výjimek, pomohl mi pochopit rozdíl mezi `except Exception` a konkrétními typy
- Ukázky z hodin – vzor pro strukturu modulu s funkcemi
