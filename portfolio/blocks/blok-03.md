# Blok 3 – 3D grafika (Blender)

## Cíl

Chtěl jsem vytvořit 3D scénu představující noční kavárnu zvenku – výloha s rozsvíceným interiérem, stůl s židlemi před vchodem a pouliční lampa. Zajímalo mě, jak v Blenderu funguje světlo a jak docílit „teplého" nočního osvětlení.

---

## Postup

Začal jsem od největších objektů – podlaha, stěna s výlohou a dveřmi. Okno jsem vyřezal pomocí Boolean operace Difference (od stěny jsem odečetl obdélníkový objekt). Stůl a židle jsem modeloval z válců a kvádrů, nožičky přes Mirror modifier.

Osvětlení dalo nejvíce práce – zkoušel jsem Point Light, ale světlo bylo příliš tvrdé. Nakonec jsem použil Area Light za výlohou simulující vnitřní osvětlení a Spot jako pouliční lampu. Výsledek je výrazně uvěřitelnější.

Renderoval jsem v Cycles, protože jsem chtěl realistické odrazy na skle. Trvalo to přibližně 8 minut na 512 vzorcích.

---

## Výstupy

- Soubor scény `kavarna.blend`
- Renderovaný výsledek:

![Render scény](../assets/images/blok3_render.png)

- Render bez a se světly (srovnání):

![Srovnání osvětlení](../assets/images/blok3_srovnani.png)

---

## Reflexe

Jsem spokojený s výsledným osvětlením – teplé světlo z výlohy na dlažbě vypadá dobře. Modelování samotné bylo rychlejší, než jsem čekal. Co mi zabralo nejvíce času, bylo nastavení materiálu skla – průhlednost v Blenderu vyžaduje správné nastavení průhlednosti v render settings, jinak je sklo černé. Příště bych si scénu lépe naplánoval dopředu – přidával jsem objekty chaoticky a pak bylo těžké je v Outlineru najít, protože jsem je nepojmenoval.

---

## Teoretické pozadí (stručně)

3D objekty se skládají z vrcholů, hran a ploch (faces) – dohromady tvoří mesh. Tvar objektu upravuji v Edit Mode, kde pracuji přímo s geometrií. Materiály definují, jak povrch reaguje na světlo – použil jsem Principled BSDF, který kombinuje různé vlastnosti povrchu (barva, lesk, průhlednost). Renderování je výpočet výsledného obrazu ze 3D scény, přičemž Cycles simuluje fyzikálně korektní pohyb světelných paprsků. Podrobnosti v `teorie.md`.

---

## Zdroje

- [https://docs.blender.org/](https://docs.blender.org/) – dokumentace Blenderu
- [https://www.youtube.com/@blenderguru](https://www.youtube.com/@blenderguru) – Blender Guru, tutoriál na zátiší
- [https://polyhaven.com/](https://polyhaven.com/) – HDRI pro okolní osvětlení (CC0)
