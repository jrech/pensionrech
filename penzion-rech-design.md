# Penzion Rech — design systém v1

Směr: Soukromý klid v zahradě. Struktura inspirovaná Hutstuf, teplá pohostinnost The Brecon. Vlastní fotografie a obsah Rechových. Pracovní textová značka Rech. není finální logo.

## Barvy

| Token | HEX | Použití |
|---|---|---|
| Ivory | #F6F3EC | Základ stránek, světlý text na tmavých plochách |
| Sand | #E8E1D5 | Dostupnost, oddělení praktických bloků |
| Olive | #303B32 | Tmavé kapitoly, nadpisy a navigace |
| Ink | #252923 | Hlavní text |
| Muted | #62675D | Doplňující text na ivory |
| Burgundy | #713D48 | Hlavní akce |
| Burgundy hover | #582E38 | Hover hlavního tlačítka |
| Line | #D6D0C4 | Dekorativní dělení; nikoli jediný indikátor ovládacího prvku |

## Typografie

Všude Rethink Sans; bez druhého fontu. Display 88/92 desktop, 56/60 mobil; nadpisy sekcí 48–56/52–60 desktop a 32/36 mobil; H3 28–40; body 18/28; navigace a tlačítka 16/24 Medium; pomocný text 14/20. Váhy 400, 500, 600. Velké nadpisy tracking přibližně -0,02 em. Text maximálně kolem 65 znaků na řádek.

## Rozložení a komponenty

- Desktop 1440 px, obsah 1280 px, okraje 80 px, 12 sloupců, mezera 24 px.
- Mobil 390 px, okraje 24 px, 4 sloupce, mezera 16 px.
- Spacing: 8, 16, 24, 32, 48, 64, 96, 128 px.
- Fotografie ostré rohy, bez stínů. Ovládání rohy 4 px a minimální výška 48 px.
- Primární tlačítko burgundy / ivory. Sekundární ivory / olive s olive obrysem.
- Focus 2 px olive, odstup 3 px; na tmavých plochách ivory. Disabled musí zůstat čitelné, loading zachová rozměr tlačítka, chyby mají konkrétní text.
- Ikony Lucide; nepoužívat emoji jako UI ikony.
- Interakce 180–240 ms, obrazové přechody 500–700 ms, respektovat omezení pohybu.

## Struktura prvního návrhu

Navigace → fotografický hero → dostupnost → příslib pobytu a obsah ceny → doporučený apartmán Desítka → wellness → zahrada a okolí → závěrečná rezervace → kontakt.

Na plátně jsou tři rámy: Design system v1, Landing page Desktop 1440 a Mobilní první obrazovka 390. Mobil je úvodní kompozice, nikoli celá homepage. Statický návrh neobsahuje funkční rezervaci. Recenze a nabídka ostatních pokojů vyžadují ověřený obsah; nebyly vymyšleny.

## Prompt pro pen.dev

Navrhni editovatelnou landing page pro Boutique penzion Rech v Blansku v Moravském krasu. Navazuj na přiložený design systém a první screen. Cílem je snadný výběr pokoje a ověření dostupnosti. Publikum: zejména páry hledající krátký odpočinek, soukromé wellness a osobní pohostinnost.

Inspirace: Hutstuf pro strukturu, velké fotografie a přehledný výběr ubytování; The Brecon pro teplou pohostinnost a komunikaci obsahu pobytu. Nekopíruj jejich logo, texty ani přesné kompozice. Použij výhradně Rethink Sans, váhy 400/500/600. Barvy: ivory #F6F3EC, sand #E8E1D5, olive #303B32, ink #252923, muted #62675D, burgundy #713D48, hover #582E38, line #D6D0C4. Burgundy vyhraď pro hlavní akce.

Vytvoř desktop 1440 px a mobil 390 px. Desktop obsah 1280 px a okraje 80 px; mobil okraje 24 px. Velké lehké nadpisy, čitelné body 18/28, fotografie bez stínů a bez zaoblení, ovládání rohy 4 px. Žádné generické bento, skleněné karty, ostrá červená ani dekorativní ikony.

Navigace: Pokoje a apartmány, Wellness, O penzionu, Kontakt a zvýrazněné Ověřit dostupnost. Hero: skutečná fotografie penzionu, čitelná kontrastní vrstva, nadpis Na chvíli jen pro sebe., stručné představení a Najít svůj pokoj. Pod hero výběr příjezdu, odjezdu a hostů s Ověřit dostupnost.

Pokračuj příslibem pobytu a jasně vysvětli snídani a all inclusive light. Představ Desítku: 2 osoby, 50 m², venkovní vířivka, finská sauna, soukromé ochlazovací jezírko, od 7 990 Kč za noc pro dva se stravou all inclusive light; cenu potvrzuje termín. Další pokoje doplň pouze z ověřených podkladů. Odliš vlastní wellness apartmánů od samostatně objednávaného wellness.

Následuje tmavá olive kapitola wellness, světlá zahrada a Moravský kras, závěrečná dostupnost a kontakt +420 777 13 23 43, recepce@penzionrech.cz. Poukazy ponech jako vedlejší nabídku. Nevymýšlej recenze, hodnocení, slevy, dojezdové časy ani vybavení pokojů. Používej reálné fotografie z přiložených assetů. Rech. je pracovní textová značka. Pojmenuj vrstvy, ulož barvy jako proměnné, tlačítka jako komponenty a zkontroluj přetečení a kontrast na obou šířkách.

## Zdroj fotografií

- https://penzionrech.cz/wp-content/uploads/2024/10/uprava1.jpg
- https://penzionrech.cz/wp-content/uploads/2021/03/penzion_rech_welness_jezirko_12.jpeg
- https://penzionrech.cz/wp-content/uploads/2021/03/penzion_rech_zahrada3.jpg

Projekt je uložen v C:/Users/rechj/Desktop/penzion rech. Exporty a fotografie jsou v penzion-rech-assets; přenositelný zdroj tří rámů a proměnných je v penzion-rech.canvas.json. Editovatelné návrhy jsou nyní v samostatném souboru rech.pen v pen.dev: design systém, desktopová landing page a mobilní úvod. Soubor spravuje pen.dev na cestě C:/Users/rechj/.pencil/documents/dc1ec0f2-da46-43d1-977b-3441fa037d8b/rech.pen. Fotografie jsou u souboru ve složce rech-assets; originály a exporty v samostatné projektové složce na ploše.


