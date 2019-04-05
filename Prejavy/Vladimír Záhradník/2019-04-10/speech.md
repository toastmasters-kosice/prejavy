# PlatformIO: Namakané Arduino IDE

## Úvod
Ahojte, v dnešnej prednáške vám predstavím PlatformIO. Vývojové prostredie, ktoré vám zjednoduší vývoj pre Arduino. Jeho hlavnou výhodou je však to, že Arduino je len jedným z podporovaných frameworkov. Nič vám nebráni vyvíjať v ňom softvér pre Raspberry Pi či Espressif. Jedno prostredie vládne všetkým! PlatformIO je však v prvom rade nástroj. Je na vás, či ho použijete. V nasledujúcich minútach vám spomeniem moje dôvody, **prečo** tento nástroj používať. Konečné rozhodnutie však bude na vás.

## Ako som sa dostal k PlatformIO
S Arduinom som sa zoznámil asi rok a pol dozadu. Kúpil som si starter kit a začal som čítať priloženú knižku. Ako jednu z prvých vecí som si nainštaloval Arduino IDE. Bolo to totiž spomenuté v návode. Páčilo sa mi, že priamo v prostredí sú dostupné príklady, ktoré viem priamo nahrať do Arduina. Na druhej strane som si takmer okamžite všimol, že v editore chýbajú funkcie, ktoré pri vývoji považujem už takmer za samozrejmosť. Vývojári Arduino IDE urobili dobrú prácu v tom, že vytvorili [jednoduché prostredie][arduino-quora] vhodné aj pre začiatočníkov, ktorí nikdy neprogramovali. A za to im patrí vďaka. Daňou za tento kompromis je strata efektivity pri vývoji a v konečnom dôsledku strata času.

Asi pred rokom som začal pracovať na väčšom komerčnom projekte pre Arduino. Má zvládať komunikáciu po [CAN zbernici][can-bus], umožňovať nastavovanie parametrov cez Bluetooth pomocou Android aplikácie, ukladanie a načítanie konfigurácie do EEPROM pamäte, ovládanie servo motorov a pritom mať stále rýchlu odozvu na príkazy od používateľa. Neviem ako vy, ale ja som si nevedel predstaviť vyvíjať takýto projekt v klasickom Arduino IDE. Hľadal som informácie na Internete. Pýtal som sa v odbornej komunite a na meetupoch. Viacerí používajú doplnok [Visual Micro][visual-micro] pre Visual Studio. Je platený. To by až tak nevadilo. Problém je, že Visual Studio beží len na Windowse. A ja vyvíjam softvér pod Linuxom. Nakoniec som sa dostal aj k PlatformIO. Vyskúšal som ho a bolo to presne to, čo som potreboval.

## Čo je PlatformIO
PlatformIO nie je len vývojové prostredie (pozn. PlatformIO > IDE na slajde). Je to celý ekosystém pre vývoj zariadení pre Internet vecí. Aktuálne podporuje 17 frameworkov, 30 platforiem a až vyše 600 embedded dosiek. Arduino tvorí len malú časť z nich. PlatformIO pozostáva z viacerých súčastí. Základ tvorí PlatformIO Core. Je to modul napísaný v Pythone, vďaka čomu nie je závislý na hardvéri, na ktorom ho spustíte. Rovnako dobre funguje na počítači ako aj na Raspberry Pi. PlatformIO Core zároveň dáva k dispozícii príkazový riadok (CLI). Pomocou neho môžete ovládať všetko potrebné. PlatformIO IDE nie je samostatná aplikácia, ale nadstavba nad existujúcim prostredím. Oficiálne je podporované Visual Studio Code od Microsoftu a tiež Atom od GitHubu. Na nasledujúcom [obrázku][vscode-atom-comparison] si môžete pozrieť porovnanie týchto dvoch prostredí. Pre ostatné vývojové prostredia si vieme vygenerovať potrebné projektové súbory cez príkazový riadok. Napríklad takto si vytvoríme projekt, ktorý vieme otvoriť v prostredí CLion (animácia).

## Výzvy na vývoj moderného softvéru
Napísať softvér je ťažké. Pritom cieľ je jasný. Kvalitný kód a [spokojný zákazník][modern-sw-development]. Ako to docieliť? Trendy v modernom softvérovom vývoji sa za uplynulé roky výrazne zmenili. Cieľ je jasný - agilný vývoj a automatizácia. Nové verzie softvéru chceme vydávať rýchlo a často. Hlavným dôvodom, prečo sa tak nedeje, je manuálne testovanie. Spravíme zmeny v kóde a potom strávime hodiny overovaním, či sme zmenou niečo nepokazili. Ak máte kód dobre otestovaný pomocou automatizovaných testov, zistíte, že ste niečo pokazili v priebehu pár sekúnd až minút.


[//]: # (Used references)
[arduino-quora]: https://www.quora.com/What-are-the-strengths-and-weaknesses-of-Arduino-and-a-typical-microcontroller-coding-limitation-price-etc
[can-bus]: https://en.wikipedia.org/wiki/CAN_bus
[visual-micro]: https://www.visualmicro.com/
[platformio]: https://platformio.org/
[vscode-atom-comparison]: https://platformio.org/#pioide-comparison
[modern-sw-development]: https://www.atlassian.com/blog/software-teams/modern-software-development-trends
[pio-unit-testing]: https://tinkerman.cat/automated-unit-testing-metal/?utm_source=platformio
[pio-unit-test-example]: https://github.com/platformio/platformio-examples/tree/develop/unit-testing/calculator