# Kontakty — audit a redesign

Datum: 20. 10. 2026. Podklady: aktuální veřejná stránka, její HTML a vizuální kontrola v prohlížeči. Návrh je ve stávajícím rech.pen a navazuje na design systém landing page.

## Co funguje

- Adresa, telefon i e-mail jsou na jedné stránce.
- Je uvedená doba telefonické dostupnosti: denně 8:30–17:30. Host ví, kdy volat a kdy raději napsat.
- Existuje kontaktní formulář s popisky polí a e-mail má přímý mailto odkaz.
- Souřadnice a vložená mapa mají pomoci s příjezdem.
- Stránka komunikuje osobní přístup a možnost nezávazného dotazu.

## Co zlepšit

### Priorita 1 — rychlý kontakt a příjezd

1. **Při mé kontrole vložená mapa zobrazila chybu „Jejda… Něco se pokazilo.“** Ověřit příčinu u mapové integrace. Toto je pozorování z konkrétní kontroly, nikoli tvrzení, že mapa selže všem návštěvníkům.
2. **Chybí výrazná přímá navigace.** Host nemá opisovat souřadnice nebo spoléhat jen na vloženou mapu. Přidat akci „Navigovat k penzionu“, která funguje nezávisle na načtení mapy.
3. **Hlavní kontakty jsou vizuálně malé.** Telefon, e-mail a adresa mají být první věcí, kterou uživatel najde. U telefonního čísla zajistit kliknutí přes tel:, u e-mailu mailto:.
4. **Formulář směšuje dotaz a rezervaci.** Pro dostupnost a cenu je vhodnější přímý odkaz na rezervační systém. Dotaz na konkrétní přání nebo nejasnost patří do formuláře.

### Priorita 2 — formulář a čitelnost

5. **Telefon je povinný i pro obyčejný e-mailový dotaz.** Doporučuji ho změnit na nepovinný. V návrhu jsou povinné jméno, e-mail a samotná zpráva; změny validace je potřeba promítnout i do serverové části.
6. **Tlačítko „Poslat“ je málo konkrétní.** „Odeslat zprávu“ jednoznačně vysvětluje akci.
7. **Fotografie na pozadí soutěží s obsahem.** Kontakt vyžaduje rychlou čitelnost. V novém návrhu je fotografie samostatná a text má klidný jednobarevný podklad.
8. **Připravit jasné chování po odeslání.** Úspěch zobrazit až po potvrzení serverem. Při chybě zachovat obsah polí a nabídnout opakování nebo přímý e-mail.
9. **Chyby vysvětlovat přímo u pole.** Nestačí barevný rámeček. U neplatného e-mailu uvést, co má uživatel opravit, a propojit vysvětlení s polem pro asistivní technologie.
10. **U formuláře doplnit dostupný odkaz na informace o zpracování údajů.** Konkrétní dokument a cílovou URL je nutné potvrdit; návrh neřeší právní posouzení zpracování.

### Priorita 3 — obsah před příjezdem

11. Na kontaktech chybí stručné informace o příjezdu a odjezdu. Časy jsou dostupné v ceníku; v návrhu jsou přeneseny na kontaktní stránku.
12. Doplnit skutečné instrukce k parkování, vjezdu a vstupu do penzionu. Pomohla by aktuální fotografie příjezdu nebo označení vchodu.
13. Potvrdit postup při pozdním příjezdu a případný kontakt pro již ubytované hosty. Nezaměňovat uvedenou telefonickou dostupnost za nepřetržitou recepci.
14. Zvážit stručnou informaci pro příjezd vlakem a bezbariérovou dostupnost, pokud je možné ji přesně doložit.
15. Doplnit identifikaci provozovatele a fakturační kontakt/údaje, pokud je hosté potřebují. Neuvádět neověřené IČO ani společnost.
16. Ve staženém HTML není obsahový H1; hlavní nadpis začíná H2. Doplnit srozumitelnou hierarchii stránky a konzistentní názvy značky.

## Nové uspořádání

1. Stejná navigace jako na landing page a nadpis „Ozvěte se nám.“
2. Výrazný telefon s telefonickou dostupností, přímý e-mail, adresa a navigace. Vše dostupné v první obrazovce mobilu.
3. Skutečný mapový podklad s vyznačenou polohou, adresou, časy příjezdu/odjezdu a nezávislým odkazem do mapové aplikace.
4. Formulář pro dotazy. Vedle něj cesta do online rezervace pro ověření termínu a ceny.
5. Stejná patička jako na dalších stránkách.

Na mobilu není úvodní dekorativní fotografie, aby nepřekážela kontaktům. Mapa a formulář následují až za přímými kontakty.

## Co je v rech.pen

- `N16f5`: Rech · Kontakty · Desktop 1440 — celá stránka.
- `out2S`: Rech · Kontakty · Mobil 390 — celá mobilní stránka.
- `BPqCl`: Rech · Kontakty · Stavy formuláře — potvrzení odeslání, chyba odeslání a neplatný e-mail.
- Rethink Sans, existující ivory/sand/olive/burgundy proměnné, stávající tlačítka a navigace.
- Skutečná fotografie zahrady a skutečný mapový podklad OpenStreetMap včetně atribuce. Mapa není ručně nakreslené schéma.

## Použité ověřené údaje

- Penzion u Rechů, Hořická 42, 678 01 Blansko — zápis převzatý z kontaktů. Před implementací sjednotit s případným úplným zápisem adresy v ostatních materiálech.
- Telefon: +420 777 13 23 43; telefonická dostupnost denně 8:30–17:30.
- E-mail: recepce@penzionrech.cz.
- Příjezd od 15:00, odjezd do 11:00 — podle ceníku.
- Poloha pinu: 49.3584477, 16.6369182 — podle mapového pinu ve zdrojovém HTML kontaktů. Před zveřejněním ověřit, že navigace vede k požadovanému vjezdu, nikoli jen k budově.

## Implementace a limity návrhu

- Návrh je statický. Formulář nebyl odeslán, nebyl kontaktován penzion a živý web nebyl změněn.
- Zachovat existující mapování polí a jejich pořadí: jméno `item_meta[7]`, e-mail `item_meta[9]`, telefon `item_meta[10]`, zpráva `item_meta[11]`. Výslovnou navrženou změnou je telefon nepovinný a zpráva povinná.
- Zachovat antispam, měření a příslušné stávající integrace; neduplikovat odeslání opakovaným kliknutím.
- Připravit stav „Odesílám…“, inline chyby, potvrzení serverem, opakování po chybě a zachování rozepsané zprávy.
- Pro úspěch/chybu použít dostupné oznámení a správu focusu. Klávesnicí musí jít obsloužit všechna pole, odkazy a tlačítka.
- Mapový poskytovatel je implementační volba. Je možné opravit existující Google integraci nebo použít jiný skutečný podklad. Zachovat potřebnou atribuci, dostupný textový kontakt a samostatný odkaz na navigaci.
- V návrhu nejsou vymyšlené informace o bezplatném parkování, nonstop recepci, bezbariérovosti ani způsobu předávání klíčů.
- Vizuálně byly zkontrolovány desktopové a mobilní exporty. Před nasazením ověřit skutečnou navigaci k vjezdu, volání, e-mail a kompletní odeslání formuláře.

## Zdroje

- [Kontakty — původní stránka](https://penzionrech.cz/kontakty/)
- [Ceník — příjezd a odjezd](https://penzionrech.cz/cenik/)
- [Online rezervace](https://penzionrech.cz/online-rezervace/)
- [OpenStreetMap — poloha](https://www.openstreetmap.org/?mlat=49.3584477&mlon=16.6369182#map=16/49.3584477/16.6369182)
- [OpenStreetMap — atribuce](https://www.openstreetmap.org/copyright)

Lokální kopie zdroje: `penzion-rech-assets/kontakty-source.html`.
