# Systémová analýza – Escape Room

**Názov projektu:** Escape Room  
**Meno riešiteľa:** Šimon Rebroš

---

## Dôvod a okolnosti zavedenia riešenia

Projekt vznikol s cieľom vytvoriť interaktívnu digitálnu Escape Room hru, ktorú je možné hrať prostredníctvom počítača alebo webového prehliadača.

Cieľom je vytvoriť zábavnú logickú hru, pri ktorej hráč postupne rieši rôzne hádanky a úlohy, získava predmety a snaží sa dostať z virtuálnej miestnosti v stanovenom časovom limite.

---

## Slovné zadanie, popis projektu od zákazníka

Cieľom projektu je vytvoriť prehľadnú a intuitívnu Escape Room hru.

Hráč sa po spustení hry dostane do virtuálnej miestnosti, v ktorej musí riešiť rôzne logické úlohy a hádanky.

Za úspešné vyriešenie úloh získava nové informácie, kódy alebo predmety, ktoré môže použiť pri ďalšom postupe.

Hra bude obsahovať časový limit, systém nápovied a možnosť vyhodnotenia výsledku hráča.

Používateľské rozhranie má byť jednoduché a zrozumiteľné aj pre používateľa, ktorý hru hrá prvýkrát.

---

## Zoznam modulov projektu a ich významných atribútov

### 1. Herný modul

**Atribúty:**
- aktuálna miestnosť
- stav hry
- zostávajúci čas
- počet vyriešených úloh

**Unikátna identifikácia objektov:** `game.id`

### 2. Modul hádaniek

**Atribúty:**
- otázka alebo zadanie
- správna odpoveď
- obtiažnosť
- stav vyriešenia

**Unikátna identifikácia objektov:** `puzzle.id`

### 3. Inventár

**Atribúty:**
- zoznam získaných predmetov
- možnosť použitia predmetu

**Unikátna identifikácia objektov:** `item.id`

### 4. Modul nápovied

**Atribúty:**
- text nápovedy
- počet dostupných nápovied
- väzba na konkrétnu hádanku

**Unikátna identifikácia objektov:** `hint.id`

### 5. Používateľské rozhranie

**Atribúty:**
- zobrazenie miestnosti
- zobrazenie úloh
- inventár
- časovač
- ovládacie prvky

**Unikátna identifikácia objektov:** `screen.id`

---

## Systémové požiadavky FURPS

### 1. Funkčnosť (Functionality – F)

- Hráč môže spustiť novú hru.
- Hráč môže riešiť jednotlivé hádanky.
- Systém kontroluje správnosť odpovedí.
- Hráč môže získavať a používať predmety.
- Hráč môže používať dostupné nápovedy.
- Systém sleduje zostávajúci čas.
- Po ukončení hry systém zobrazí výsledok hráča.

### 2. Vhodnosť k použitiu (Usability – U)

- Jednoduché a prehľadné používateľské rozhranie.
- Hra bude ovládateľná pomocou myši a klávesnice.
- Hráč bude jasne vidieť zostávajúci čas, inventár a aktuálnu úlohu.
- Hra nebude vyžadovať predchádzajúce skúsenosti používateľa.

### 3. Spoľahlivosť (Reliability – R)

- Hra musí správne kontrolovať odpovede hráča.
- Časovač musí fungovať počas celej hry.
- Postup hráča sa počas hrania nesmie svojvoľne stratiť.
- Jedna chyba používateľa nesmie spôsobiť pád celej aplikácie.

### 4. Výkon (Performance – P)

- Hra nebude vyžadovať výkonný hardvér.
- Jednotlivé obrazovky a úlohy sa budú načítavať bez výrazného oneskorenia.
- Kontrola odpovede bude vykonaná prakticky okamžite.

### 5. Schopnosť údržby (Supportability – S)

- Do hry bude možné jednoducho pridávať nové hádanky.
- Bude možné upravovať existujúce úlohy bez potreby meniť celý program.
- Projekt bude rozdelený do samostatných modulov, aby bolo jednoduchšie opravovať chyby alebo pridávať nové funkcie.

---

## Kritické situácie

### 1. Systémové

- Chyba pri načítaní hry alebo niektorej miestnosti.
- Chyba pri ukladaní aktuálneho stavu hry.
- Nesprávne fungovanie časovača.

### 2. Aplikačné

- Hráč zadá neplatný vstup.
- Hráč sa pokúsi použiť predmet na nesprávnom mieste.
- Hráč sa pokúsi pokračovať bez vyriešenia potrebnej úlohy.
- Hráč vyčerpá všetky nápovedy.

---

## Tri situácie definujúce hranice systému

### 1. Ideálny scenár

Hráč spustí hru, postupne vyrieši všetky hádanky, správne používa získané predmety a dostane sa z Escape Room pred vypršaním časového limitu.

### 2. Hranične riešiteľný scenár

Hráč nevie vyriešiť niektorú z hádaniek.

Použije dostupnú nápovedu a pokračuje ďalej.

Hru stále dokáže úspešne dokončiť.

### 3. Situácie, ktoré aplikácia nezvládne

Hráč nevyrieši potrebnú hádanku, vyčerpá všetky nápovedy a bez správneho riešenia sa nedokáže dostať do ďalšej časti hry.

---

## Kontext prostredia

Aplikácia bude fungovať na počítači.

Konkrétna forma používateľského rozhrania bude závisieť od zvoleného programovacieho jazyka a použitej technológie.

Na používanie aplikácie nebude potrebný žiadny špeciálny hardvér ani externé zariadenie.

---

## Charakteristika aktérov a prostredia

### Aktéri

- Hráč
- Administrátor / tvorca hry

### Prostredie

- počítač alebo notebook
- grafické alebo webové používateľské rozhranie

Hráč používa aplikáciu na hranie Escape Room hry.

Administrátor môže pridávať alebo upravovať hádanky, predmety a ďalší obsah hry.

---

## Use Case diagram

![Use Case diagram](use%20case%20diagram.png)

---

## Scenáre – konkrétna implementácia Use Case

### 1. Vyriešenie hádanky

**Názov:** Vyriešenie hádanky

**Kontext:**  
Hráč chce vyriešiť úlohu, aby mohol pokračovať v Escape Room.

**Level zanorenia Use Case:**  
Hlavný scenár

**Aktéri:**  
Hráč, systém

**Stakeholderi a záujmové osoby:**  
Hráč, administrátor hry

### Vstupné podmienky

- Hráč má spustenú hru.
- Hráč sa nachádza pri aktívnej hádanke.
- Hra ešte nebola ukončená.

### Výstupné podmienky

- Systém vyhodnotí odpoveď hráča.

### Minimálny výstup

Systém oznámi hráčovi, či bola odpoveď správna alebo nesprávna.

### Ideálny výstup

Hráč zadá správnu odpoveď, úloha sa označí ako vyriešená a odomkne sa ďalšia časť hry.

### Hlavný scenár

1. Hráč otvorí hádanku.
2. Systém zobrazí zadanie.
3. Hráč zadá odpoveď.
4. Systém porovná odpoveď so správnym riešením.
5. Odpoveď je správna.
6. Systém označí hádanku ako vyriešenú.
7. Hráč získa predmet, kód alebo prístup k ďalšej časti hry.

### Rozšírenie

- Ak je odpoveď nesprávna, systém upozorní hráča a umožní mu skúsiť odpovedať znova.
- Ak hráč nevie odpoveď, môže použiť nápovedu.
- Ak časový limit vyprší, hra sa ukončí.

---

## Sekvenčný diagram

![Sekvenčný diagram](sekvencny%20diagram.png)

---

## Triedny diagram

![Triedny diagram](triedny%20diagram.png)
