# Teorie – Blok 4: Fyzické počítání (Arduino)

## Co jsem se naučila

Pochopila jsem, že programování mikrokontroléru je jiné než psaní konzolové aplikace – program běží na fyzickém čipu bez operačního systému, neustále dokola, a musím uvažovat o časování, pinech a napájení. Propojení kódu s fyzickým světem (rozsvícení LED, zobrazení na displeji) bylo pro mě nový způsob myšlení.

---

## Struktura Arduino programu

Arduino program (sketch) má vždy dvě povinné funkce:

```cpp
void setup() {
  // Spustí se jednou při startu
  pinMode(13, OUTPUT);
  Serial.begin(9600);
}

void loop() {
  // Opakuje se neustále dokola
  digitalWrite(13, HIGH);
  delay(500);
  digitalWrite(13, LOW);
  delay(500);
}
```

Rozdíl oproti Pythonu: Arduino nemá `print()` – místo toho používám `Serial.println()` a výstup čtu v Serial Monitoru v Arduino IDE.

---

## Digitální a analogové piny

**Digitální pin** zná jen dva stavy: HIGH (5 V) nebo LOW (0 V). Slouží pro LED, tlačítka, bzučáky.

**Analogový pin** (A0–A5) čte hodnoty od 0 do 1023 pomocí AD převodníku. Slouží pro potenciometry, senzory světla nebo teploty s analogovým výstupem.

**PWM pin** (označený vlnovkou ~) umožňuje simulovat analogový výstup rychlým přepínáním. Používám ho pro stmívání LED nebo servo motory. Funkce: `analogWrite(pin, 0–255)`.

---

## I2C sběrnice

I2C je komunikační protokol umožňující propojit více zařízení jen dvěma vodiči (SDA = data, SCL = hodiny). Každé zařízení má unikátní adresu (hexadecimální číslo, např. `0x27`). Arduino jako „master" se zařízení ptá na data nebo mu posílá příkazy. Výhoda: místo 10 propojení pro displej stačí 4 (VCC, GND, SDA, SCL).

---

## Knihovny

Arduino IDE umožňuje instalovat knihovny – hotové balíčky kódu pro konkrétní komponenty. Přidám je přes Library Manager (`Sketch → Include Library → Manage Libraries`). Po instalaci importuji:

```cpp
#include <DHT.h>
#include <LiquidCrystal_I2C.h>
```

Knihovny mi ušetřily psaní nízkoúrovňového kódu pro komunikaci s čidlem a displejem.

---

## Ladění přes Serial Monitor

Bez Serial Monitoru bych jen hádala, co program dělá. Výpis hodnot mi ukázal, kdy čidlo vrací `NaN` (chyba čtení) a kdy vrací reálnou teplotu:

```cpp
Serial.print("Teplota: ");
Serial.println(teplota);
```

Je to ekvivalent `print()` z Pythonu – základní nástroj ladění.

---

## Slovník pojmů

---

**Mikrokontrolér**
Malý počítač na jediném čipu – obsahuje procesor, paměť a vstupně-výstupní periferie. Na rozdíl od počítače nemá operační systém a je určen pro řízení konkrétního hardwaru.

---

**Arduino**
Open-source platforma kombinující mikrokontrolér (ATmega) s vývojovou deskou a prostředím Arduino IDE. Programuje se v jazyce C++ s Arduino knihovnou.

---

**Pin**
Fyzický kontakt na desce Arduino, přes který se připojují komponenty. Může být digitální nebo analogový, vstupní nebo výstupní.

---

**`setup()`**
Funkce v Arduino programu, která se spustí jednou při startu nebo resetu. Inicializuji zde piny, sériovou komunikaci a knihovny.

---

**`loop()`**
Funkce v Arduino programu, která se opakuje neustále dokola. Veškerá logika programu běží zde (nebo ve funkcích volaných odtud).

---

**`pinMode()`**
Funkce nastavující pin jako vstup (`INPUT`) nebo výstup (`OUTPUT`). Musím ji zavolat v `setup()` pro každý pin, který používám.

---

**`digitalWrite()`**
Zápis hodnoty HIGH nebo LOW na digitální výstupní pin. HIGH = 5 V, LOW = 0 V.

---

**`digitalRead()`**
Čtení stavu digitálního vstupního pinu. Vrátí HIGH nebo LOW – např. zda je tlačítko stisknuté.

---

**`delay(ms)`**
Pozastaví program na zadaný počet milisekund. Jednoduchý, ale blokuje celý program – nic jiného se během čekání nevykoná.

---

**`Serial.begin()` / `Serial.println()`**
Inicializace sériové komunikace a výpis hodnot do Serial Monitoru. Používám pro ladění – zobrazím si hodnoty proměnných, aniž bych měla fyzický displej.

---

**PWM (Pulse Width Modulation)**
Metoda simulace analogového výstupu rychlým přepínáním digitálního signálu. Střída (duty cycle) 0–100 % odpovídá hodnotě 0–255 ve funkci `analogWrite()`.

---

**Breadboard (nepájivé pole)**
Deska s propojovacími otvory pro rychlé prototypování bez pájení. Sloupce uprostřed jsou propojeny horizontálně, lišty na okrajích vertikálně (napájení).

---

**Pull-up rezistor**
Rezistor zapojený mezi pin a napájení (+5 V), který drží pin ve stavu HIGH, dokud tlačítko nepropojí pin se zemí (GND). Zabraňuje „plovoucímu" nedefinovanému stavu pinu. Arduino má vestavěné pull-up rezistory aktivovatelné přes `INPUT_PULLUP`.

---

**I2C (Inter-Integrated Circuit)**
Dvouvodičová komunikační sběrnice pro propojení více zařízení. Každé zařízení má unikátní adresu. Použila jsem ji pro displej LCD.

---

**`isnan()`**
Funkce testující, zda je hodnota „Not a Number" (NaN) – speciální stav při chybě čtení z čidla. Použila jsem ji k zachycení chyby DHT11.

---

## Zdroje

- [https://docs.arduino.cc/language-reference/](https://docs.arduino.cc/language-reference/) – reference funkcí
- [https://www.tinkercad.com/](https://www.tinkercad.com/) – simulátor
- [https://randomnerdtutorials.com/](https://randomnerdtutorials.com/) – praktické návody
