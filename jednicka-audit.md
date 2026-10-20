# Jednička — audit detailu apartmá a návrh redesignu

Audit: 20. 10. 2026. Podklady: aktuální veřejná stránka, její HTML a galerie, dodaný screenshot, ceník a informace o stravování. Návrh v aktuálním `rech.pen`; návrh je statický, rezervační systém není zapojený.

## Co funguje

- Jednička má výrazný vlastní charakter: tropická zahrada a soukromé wellness. Nabídka se dobře odlišuje od běžného dvoulůžkového pokoje.
- Stránka uvádí cenu od 7 990 Kč za noc pro dvě osoby a říká, že obsahuje all inclusive light. Základ ceny je tedy srozumitelný.
- Jsou uvedené důležité parametry: 80 m², postel 180 × 200 cm, swim spa s protiproudem, finská sauna a kino s úhlopříčkou 4 m.
- Fotografie ukazují skutečné prostředí za dne i večer. V galerii je osm fotografií.
- Existují cesty k rezervaci i ke koupi pobytu jako dárku.

## Co je špatně a proč

### Priorita 1 — pomoci hostovi rozhodnout se

1. **Chybí představení samotného interiéru.** Galerie ukazuje venkovní wellness, zahradu a detail sprchy. Nevidím ložnici, koupelnu ani kino. Při rozhodování o noclehu chybí zásadní důkaz, kde budu spát a jak vypadá vnitřní prostor.
2. **Fotografie na dodaném širokém screenshotu zabírají málo prostoru.** Nabídka stojí skoro 8 tisíc za noc, ale působí jako malý katalogový záznam. Potřebuje velkou fotografii a čitelné náhledy.
3. **Přednosti nemají hierarchii.** Sauna, protiproud a kino mají větší rozhodovací hodnotu než Wi-Fi nebo fén. Patří do rychlého přehledu nahoře; běžné pohodlí může být níže.
4. **Rezervace vede na obecnou stránku.** Odkaz je `/online-rezervace/` bez identifikace pokoje v URL. Při implementaci zachovat Jedničku, termín i počet hostů až do dostupnosti a objednávky. Podporu konkrétních parametrů musí potvrdit integrace Previo.
5. **„All inclusive light“ potřebuje vysvětlení přímo u ceny.** Host nemá odhadovat, zda jde o snídani, bufet, večeři nebo nápoje.

### Priorita 2 — důvěra a použitelnost

6. **Není jasná maximální kapacita.** Cena pro dvě osoby není totéž co potvrzení maximálního počtu hostů, dětí nebo přistýlek.
7. **Chybí provozní odpovědi k wellness.** Celoroční provoz, teplota vody, případná omezení hodin a přesný rozsah užívání v ceně. Také vyjasnit míru vizuálního soukromí; „soukromé“ nemusí automaticky znamenat bez možnosti pohledu z okolí.
8. **Praktické informace jsou jinde na webu.** Příjezd, odjezd, mazlíčci, podmínky platby a storna mají být dostupné přímo na detailu.
9. **Galerie má slabé obsahové popisky.** Zdrojové názvy jako „Snímek obrazovky…“ nebo „IMG_0166“ nevysvětlují záběr. Doplnit popisky a smysluplné alternativní texty.
10. **Typografie, červené akcenty a tlačítka nevytvářejí klidnou hierarchii.** Pro boutique prezentaci použít větší písmo, konzistentní šířku obsahu a jedinou výraznou akční barvu pro rezervaci.

### Priorita 3 — obsah a technická kvalita

11. Hlavní nadpis H1 je v HTML cena; název Jednička je H2. Použít H1 „Jednička — wellness apartmá v Blansku“, případně viditelnou zkrácenou variantu „Jednička“ a popisný title.
12. Title „Jednicka - Penzion u Rechů“ neříká, čím je pokoj specifický. Ve staženém HTML jsem nenašel samostatnou meta description. Doplnit popis, sdílecí obrázek a relevantní údaje o ubytování; žádné neověřené hodnocení.
13. Opravit překlepy „swimm spa“, „bazém“, formát Kč a zápis jednotek.
14. Případnou recenzi vybírat od ověřeného hosta Jedničky. Obecnou recenzi penzionu jasně označit jako obecnou.

## Doporučené pořadí stránky

1. Navigace stejná jako na landing page; návrat na pokoje.
2. Název, jedna věta charakteru, cena s jednotkou a zahrnutým stravováním.
3. Velká galerie: denní celek, ložnice, koupelna, wellness, sauna, kino, večerní atmosféra. Současný návrh používá dostupné skutečné venkovní fotografie.
4. Rychlé parametry: rozloha, pobyt pro dva, soukromé swim spa, sauna, kino.
5. Krátký příběh apartmá a vysvětlení tří hlavních předností. Vedle výběr termínu, cena „od“, hosté a hlavní akce „Ověřit dostupnost“.
6. Pohodlí v pokoji a konkrétní vybavení.
7. Co obsahuje cena: snídaně a all inclusive light, s časy a odkazem na podrobnosti.
8. Příjezd, odjezd, mazlíčci a krátké odpovědi na otázky před rezervací.
9. Dvě alternativní apartmá pro případ, že Jednička nevyhovuje nebo je obsazená.
10. Kontakt a patička.

Na mobilu: fotografie přes celou šířku, přehledná galerie a fixní spodní lišta s cenou a akcí „Vybrat termín“. Lišta otevře rezervační panel a respektuje bezpečný spodní okraj zařízení. Po výběru termínu nahradit orientační cenu skutečnou nabídkou a uvést celkovou cenu i případné poplatky před potvrzením.

## Co si vzít z referencí

| Reference | Co převzít | Jak je to použité v návrhu |
|---|---|---|
| Hutstuf — Beaver | Podrobné představení konkrétního ubytování, fotografie interiéru i exteriéru, oddělené přednosti a praktické informace | Velká galerie, vysvětlení swim spa/sauny/kina a sekce před příjezdem |
| The Brecon — Rooms | Každý pokoj má stručný charakter a několik jasně pojmenovaných rozdílů | „Váš soukromý tropický úkryt“ a rychlý přehled předností |

Pro Rech doporučuji spojit atmosféru s přehledným výběrem termínu. Rozhodování o konkrétním pokoji vyžaduje více konkrétních údajů než úvodní landing page.

## Co bylo vytvořeno v rech.pen

- `D2lr3`: Rech · Jednička · Detail apartmá · Desktop 1440 — celá stránka.
- `JKkuQ`: Rech · Jednička · Detail apartmá · Mobil 390 — celá mobilní stránka.
- `Jk9dp`: Rech · Jednička · Mobilní viewport a fixní rezervace — první obrazovka s rezervační lištou.
- Rethink Sans, existující proměnné ivory/sand/olive/burgundy, existující primární tlačítko a navigační prvky.
- Všechny fotografie pocházejí z webu Rech. Žádná ilustrační ani generovaná fotografie interiéru.

## Před zveřejněním doplnit nebo potvrdit

- Reálné fotografie ložnice, koupelny a kina. V tmavé sekci o pohodlí doporučuji následně nahradit venkovní záběr fotografií interiéru.
- Půdorys se skutečnými rozměry a vztah interiéru k venkovnímu wellness; nevymýšlet dispozici z fotografie.
- Maximální obsazenost, přistýlky a pravidla pro děti; co přesně zahrnuje plocha 80 m².
- Koupelna, klimatizace, parkování, župany a osušky — na detailu nejsou potvrzené. Do návrhu nebyly přidány jako fakta.
- Sezónnost a provoz wellness, případné poplatky, místní poplatek a minimální délka pobytu.
- Konzistentní platební a storno podmínky. Aktuální ceník výslovně nevymezuje interval mezi 14 a 29 dny před příjezdem; před přepisem podmínek sjednotit s provozovatelem.
- Napojení termínu a Jedničky do Previo; stavy bez termínu, načítání, dostupné, obsazené a chyba. Návrh neukazuje vymyšlenou dostupnost.
- Při implementaci otestovat klávesnici, focus, lightbox, výběr termínu, skutečné mobilní rozměry a návaznost rezervace. Statický návrh tyto interakce neověřuje.

## Zdroje

- [Jednička — aktuální detail](https://penzionrech.cz/jednicka/)
- [Ceník a praktické podmínky](https://penzionrech.cz/cenik/)
- [All inclusive light](https://penzionrech.cz/all-inclusive-light/)
- [Online rezervace](https://penzionrech.cz/online-rezervace/)
- [Hutstuf — Beaver](https://hutstuf.com/hut/beaver/)
- [The Brecon — Rooms](https://thebrecon.com/en/rooms/)

