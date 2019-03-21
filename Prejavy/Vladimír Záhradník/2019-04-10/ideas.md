# Nápady
Čím sa líšia Arduino IDE od PlatformIO? Aké sú pozitíva a nedostatky? Ako ovplyvňujú prácu programátora, jeho workflow? A čo Atmel Studio?

## Animovaný CLI gif
https://superuser.com/questions/1158180/capture-cli-output-as-animated-gif
https://itsfoss.com/best-gif-recorder-linux/

- Spolupráca viacerých členov pri vývoji, cloud IDE
- Automatizácia a unit testy
- Produktivita pre vývojára, rapid development
- TDD?

## Arduino IDE
- Napísaný v Jave
- [x] Dokumentácia na oficiálnych stránkach
- [x] Oficiálne IDE pre Arduino
- [x] Súčasťou distribúcie sú príklady pre Arduino zoradené do kategórií
- [x] Priamo v menu sú odkazy na oficiálnu dokumentáciu, je však potrebné internetové pripojenie (časť je dostupná offline)
- [x] Používa interný gcc kompilátor, čo eliminuje časť problémov na rôznych systémoch
- [x] Programy napísané v Arduino IDE sa volajú "sketches" a majú príponu .ino. Oproti C-čkovskému súboru skrývajú pred používateľom hlavičku Arduino.h.
- [x] Verifikácia zostavenia programu pred uploadom do Arduina
- [x] Arduino bootloader umožňuje nahrávať program po USB. Je možné ho prepísať a program "naprogramovať", čím sa ušetrí nejaké miesto na flash pamäti
- [x] Podpora hardvérových programátorov pre zápis programu na čip
- [x] Podpora pre vyhľadávanie kľúčových slov v referenčnej príručke. Slová sú definované v KEYWORDS.txt
- [x] Pridanie vlastnej knižnice do Library Managera je jednoduché. Viac tu, vrátane obmedzení: https://github.com/arduino/Arduino/wiki/Library-Manager-FAQ
- [ ] Funkcionalita pre prácu s hardvérom je súčasť IDE
- [ ] Library Manager neumožňuje špecifikovať iný ako oficiálny zoznam knižníc, tiež neumožňuje zadať priamy odkaz na knižnicu, ktorú chceme stiahnuť
- [ ] Podporuje len dosky kompatibilné s Arduino Frameworkom
- [ ] Vyžaduje inštaláciu OpenJDK7/JRE
- [ ] Inštalácia Arduino IDE na niektorých linuxových platformách (napr. Debian) vyžaduje stiahnutie a priame nainštalovanie balíka. Verzia v repozitári je upravená, funkčne obmedzená a zastaralá
- [ ] Detekcia chýb v prostredí je veľmi jednoduchá. Je označený problematický riadok a chyba kompilátora je vypísaná dola. Nie je možné sa preklikať na definíciu funkcie
- [ ] Arduino Sketches (projekty) neumožňujú zadefinovať závislosti, t.j. ktoré knižnice projekt potrebuje, v akej verzii. Knižnice musí používateľ inštalovať sám
- [ ] Inštalácia knižnice prebieha ručne. V menu "Správa knižníc" je možné vybrať verziu knižnice. Pre knižnice, ktoré nie sú v zozname, je možné ručne pridať .zip
- [ ] Veľa vecí je pred používateľom ukrytých
- [ ] Arduino IDE nepodporuje verzovacie systémy ako Git. Nie je možné porovnávať históriu zmien; archivácia projektu je do .zip archívu
- [ ] Integrované zvýrazňovanie syntaxe sa spolieha na súbor keywords.txt definovaný autorom knižnice. Bez tohto súboru nezvýrazní vhodnou farbou triedy, funkcie ani konštanty. Formát nie je dobre zdokumentovaný a treba pozrieť ako súbor definujú ostatné populárne knižnice. https://
spencer.bliven.us/index.php/2012/01/18/arduino-ide-keywords/ https://github.com/arduino-libraries/Servo/blob/master/keywords.txt
- [ ] Chýba code completion, náhľad definície funkcie, príp. popisu funkcie
- [ ] Knižnice sa inštalujú do spoločného adresára (Arduino/libraries) a nie je možné používať rôzne verzie knižnice pre rôzne projekty

## PlatformIO
- PlatformIO Core napísaný v Pythone, rozšírenia pre VSCode v JavaScripte?
- Základ tvorí PlatformIO Core (CLI) a pluginy/rozšírenia do viacerých IDE (v podstate wrappujú PIO Core do GUI). Ako hlavné sú podporované Visual Studio Code a Atom (VSCode podporuje viac funkcií).
- [] PlatformIO Core je kompatibilné s Pythonom 2.7. Python 3 nie je zatiaľ úplne podporovaný, ale na podpore sa pracuje
- [x] Apache 2.0 licencia - možnosť použiť PlatformIO v komerčných aj nekomerčných projektoch
- [x] PlatformIO Core je multiplatformové a bez problémov beží aj na RPi
- [x] Dokumentácia na oficiálnych stránkach
- [x] IDE je oddelené od hlavnej funkcionality, ktorá rieši kompiláciu, flashovanie, atď.
- [x] Možnosť ovládať celé PlatformIO len cez CLI
