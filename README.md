# KOMPLETNÍ POPIS REZERVAČNÍHO SYSTÉMU EZO-ESHOPU

## CSS ČÁST
- Nastavuji tmavě šedé pozadí (#1e1e1e) a oranžový text pro celé tělo dokumentu
- Vytvářím flex kontejner pro tlačítka s mezerami 10px
- Definuji responzivní chování tlačítek: min-width 130px, max-width 150px
- Přidávám spodní okraj 40px pro všechny kontejnery
- Vytvářím jednotný styl pro všechny vstupní prvky a tlačítka
- Nastavuji náhledovému obrázku 200x200px s object-fit: cover
- Definuji tmavý styl pro textové prvky s oranžovým ohraničením
- Přidávám focus efekty: změnu barvy ohraničení a pozadí
- Navrhuji tlačítka s přechody a stíny: oranžové pozadí, kaštanový text
- Vytvářím hover efekt: zesvětlení barvy a zvětšení stínu
- Přidávám aktivní stav tlačítek: tmavě růžová barva bez stínu
- Navrhuji podklad modálního okna s černým průhledným pozadím
- Vytvářím styl obsahu modálního okna: tmavé pozadí, oranžový text, oranžový rámeček
- Nastavuji pozici tlačítka pro zavření modálního okna (křížek vpravo nahoře)
- Vytvářím speciální styl pro hlavní tlačítko: kaštanové pozadí, bílý text, oranžový stín

## HTML STRUKTURA
- Přidávám nadpis "OTÁZKY PRO DIAGNOSTIKU"
- Vytvářím kontejner pro 13 tematických tlačítek (O-MNĚ, EZOTERIK, VZTAHY...)
- Speciální tlačítko "O-MNĚ" má odlišný vizuální styl
- Připravuji modální okno pro zobrazení obsahu s textem "Načítání obsahu..."
- Vytvářím oddělovací čáru a prázdné řádky pro vizuální členění
- Přidávám formulář pro objednávku s nadpisem "OBJEDNÁVKOVÝ SYSTÉM"
- Vkládám vstup pro telefonní číslo (max 9 číslic)
- Přidávám kalendář pro výběr data s minimem nastaveným na dnešek
- Vytvářím rozbalovací seznam pro výběr času (bude dynamicky naplněn)
- Přidávám možnost nahrát fotografii s náhledem
- Vytvářím textové pole pro poznámku klienta
- Přidávám tlačítka "Uložit" a "Reset"
- Vytvářím sekci pro kontrolu odpovědi se zlatým nadpisem
- Přidávám vstup pro telefonní číslo pro načtení rezervace
- Připravuji výstupní oblast pro zobrazení načtených dat

## JAVASCRIPT FUNKCE
### Inicializace po načtení stránky
- Nastavuji minimální a výchozí datum na dnešek
- Generuji časové sloty od 10:00 do 20:00 hodin
- Přidávám posluchač události pro náhled obrázku po nahrání

### Funkce otevriModal(nazev)
- Zobrazuji modální okno s textem "Načítám..."
- Načítám obsah z externího HTML souboru (./modaly/[nazev].html)
- Při chybě zobrazuji chybové hlášení s detaily
- Zobrazuji načtený obsah v modálním okně

### Funkce zavriModal(udalost)
- Zavírám modální okno při kliknutí na pozadí nebo křížek
- Kontroluji, zda bylo kliknuto na pozadí modálního okna

### Funkce ulozData()
- Validuji telefonní číslo (musí být 9 číslic)
- Převádím nahranou fotku do Base64 formátu
- Generuji XML strukturu s daty klienta
- Vytvářím a automaticky stahuji XML soubor
- Po uložení resetuji formulář

### Funkce nactiData()
- Umožňuji načíst uložený XML soubor
- Zobrazuji data pokud:
  - Zadané telefonní číslo odpovídá uloženému
  - Je zadáno heslo "000000000" (režim terapeuta)
- V režimu terapeuta umožňuji editaci terapeutovy poznámky
- Zobrazuji náhled uložené fotky

### Funkce ulozPoznamku()
- Získávám data z výpisu pomocí regulárních výrazů
- Generuji nový XML soubor s aktualizovanou terapeutovou poznámkou
- Automaticky stahuji aktualizovaný XML soubor
- Informuji uživatele o úspěšném uložení

### Funkce resetujFormular()
- Resetuji všechny formuláře na stránce
- Nastavuji datum na dnešek
- Čistím náhled fotky
- Mažu výstupní oblast
