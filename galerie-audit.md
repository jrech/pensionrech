# Fotogalerie — audit a redesign

Datum: 20. 10. 2026. Podklady: veřejná stránka, její HTML, inventura fotografií a otevřený zvětšený náhled v prohlížeči. Návrhy jsou ve stávajícím rech.pen a používají design systém landing page.

## Co je dobré

- Autentické fotografie konkrétního penzionu. Zahrada, lidé, jídlo a večerní atmosféra pomáhají představit si pobyt.
- Existující tematické rozdělení: Terasa a zahrada, Interiér penzionu, Gastronomie.
- Ve veřejné stránce je 24 fotografií: 12 zahrada, 4 interiér a 8 gastronomie.
- Zvětšení fotografie funguje; otevřený náhled obsahuje počet fotografií a ovládací prvky pro zavření i přechod mezi snímky.
- Většina obrázků má odložené načítání. Tento princip zachovat.

## Co zlepšit

### Priorita 1 — orientace a rozhodování

1. **Galerie neobsahuje vlastní skupinu pokojů a wellness.** Návštěvník hledající pokoj musí odejít do menu. Doplnit fotografie z detailů apartmá a vždy pojmenovat konkrétní pokoj.
2. **„Interiér penzionu“ ukazuje hlavně jídelní a společné prostory.** Není to náhrada za fotografie ložnic a koupelen. Tyto dvě věci obsahově rozlišit.
3. **Každá větší skupina má vlastní stránkování.** Zahrada má 12 položek rozdělených po čtyřech, gastronomie 8 po čtyřech. Pro tento počet fotek je přehlednější jedna galerie s filtry a postupným odhalením dalších snímků.
4. **Z fotografií pokojů musí vést cesta na jejich detail.** Kliknutí na snímek otevře velký náhled; samostatná jasná akce nabídne detail konkrétního apartmá.

### Priorita 2 — prezentace

5. **Nadpisy a samotné galerie nemají na pozorovaném desktopovém rozložení jednotnou osu.** Sjednotit obsahovou šířku, okraje a vertikální mezery.
6. **Náhledy jsou stejně významné a silně oříznuté.** Vytvořit výběr hlavních snímků a střídat větší celky s detaily. Zvětšený náhled vždy zobrazí celý obraz bez ořezu.
7. **Chybí užitečné popisky.** Uživatel má vědět, zda se dívá na společnou zahradu, konkrétní apartmá, nebo jídelnu.
8. **Zvětšená fotografie ukazuje technický název souboru.** Při kontrole první fotografie byl popisek `20230912_113622`. Nahradit názvem „Zahrada s jezírky“ a zobrazit kategorii.
9. **Míchá se čeština a angličtina.** Pozorované „Next“, „1 of 12“ a „Close (Esc)“ sjednotit do češtiny.
10. **Stránka po prohlížení nevede dál.** Doplnit klidné zakončení „Našli jste své místo?“ s cestou k pokojům. Rezervaci ponechat dostupnou i v hlavní navigaci.

### Priorita 3 — přístupnost a rychlost

11. V inventuře HTML nemělo žádné z 24 obsahových fotografií neprázdný atribut alt. Doplnit věcný popis; nevkládat do něj marketing ani opakované klíčové fráze.
12. Při implementaci zajistit srozumitelné názvy tlačítek, viditelný focus, správu focusu v dialogu, zavření Escape a návrat na původní fotografii. Kompletní průchod klávesnicí nebyl v rámci auditu ověřen.
13. Připravit správně velké náhledy, rozměry a responzivní varianty; původní fotografie načítat až pro zvětšení. Ověřit správnost existujícího srcset a sizes.
14. Filtrování a načítání dalších snímků nemá ztratit pozici uživatele. Změnu počtu výsledků oznámit i asistivním technologiím.

## Nový návrh v rech.pen

- **Desktop — `y256fB`:** velká typografie, fotografie ve střídajících se dvou- a třísloupcových řadách, popisky pod snímky, filtry a načtení dalších fotografií.
- **Mobil — `H3dkpL`:** všechny kategorie viditelné ve dvou řádcích, kombinace velkých fotek a dvojic, stejné popisky a postupné načítání.
- **Zvětšená fotografie desktop — `ui9HV`:** celý snímek bez ořezu, předchozí/další, zavření, kategorie a pořadí, náhledy okolních snímků a cesta na detail pokoje.
- **Zvětšená fotografie mobil — `zMnOX`:** celý snímek, jasné ovládání a detail pokoje. Při implementaci doplnit i swipe; tlačítka zůstávají dostupná.
- Rethink Sans, existující ivory/sand/olive/burgundy proměnné, stávající primární a sekundární tlačítko, navigace a patička.

## Fotografie a počty v návrhu

Návrh počítá s celkem **28 fotografiemi**: 24 z původní galerie a 4 skutečné fotografie z detailů apartmá — Desítka, Devítka a dva záběry Jedničky. Nové číslo není popisem současné veřejné stránky.

Filtry: Vše 28, Pokoje a wellness 4, Zahrada 12, Interiér 4, Gastronomie 8. První sada ukazuje 12 fotografií a tlačítko nabídne dalších 16. Po filtrování se počet i text načítání přepočítá podle výsledků.

Při přípravě finálního obsahu je vhodné doplnit více skutečných fotografií ložnic a koupelen. Výběr a počty se pak upraví podle výsledné knihovny. Fotografie místnosti nepřiřazovat k jinému pokoji pouze podle podobného vzhledu.

## Chování pro implementaci

1. Filtr mění výsledky v téže galerii. Aktivní stav je viditelný i bez spoléhání jen na barvu. Při příchodu z detailu pokoje lze otevřít příslušnou sadu fotografií.
2. Kliknutí na snímek otevře dialog na jeho správné pozici. Pořadí odpovídá právě zvolené kategorii; např. po filtrování pokojů bude počet 4, nikoli 28.
3. V dialogu fungují šipky, Escape, focus a na mobilu swipe. Zavření zachová kategorii a vrátí pozici i focus na původní snímek.
4. Akce „Prohlédnout Desítku“ vede na detail Desítky. Základní kliknutí na fotografii a odkaz na pokoj mají odlišnou, jednoznačnou funkci.
5. Další fotografie se načtou na vyžádání, bez návratu na začátek a bez náhlého posunu rozložení. Při poslední sadě zmizí tlačítko.
6. Připravit načítání, chybu fotografie a případně nulový výsledek budoucí kombinace filtrů. Bez vymyšlené dostupnosti pokojů.

Jde o statický design: filtry, lightbox a odkazy nejsou v návrhu zapojené do fungujícího webu. Ověřeno bylo vizuální rozložení exportů a neprázdné rozměry prvků. Před publikací je potřeba ověřit skutečné interakce a přístupnost.

## Zdroje

- [Původní fotogalerie](https://penzionrech.cz/fotogalerie/)
- [Jednička](https://penzionrech.cz/jednicka/)
- [Desítka](https://penzionrech.cz/project/wellness-desitka/)
- [Devítka](https://penzionrech.cz/project/wellness-apartma-nad-jezirkem/)

Lokální inventura původních 24 snímků: `penzion-rech-assets/galerie-inventory.json`. Původní HTML je uložené v `penzion-rech-assets/galerie-source.html`.
