# Osnova

### O čom je táto prednáška
1. Úvod
2. Ako som sa dostal k PlatformIO
3. Čo je PlatformIO

### Aké problémy PlatformIO rieši
1. V Arduino IDE chýba funkčnosť moderných editorov
  * Zvýrazňovanie syntaxe v Arduino IDE
    * Keywords.txt - sme závislí od autora knižnice
 - Intelligent code completion
 - Náhľad definície funkcie a možnosť prepnúť sa na odkazovaný kód
 - Riešenie: PlatformIO a podpora viacerých IDE

2. Podpora pre verzovacie systémy
  * Git, SVN, ... podpora závisí od použitého IDE

3. Formát Arduino Sketch (.ino)
  * Štruktúra formátu a porovnanie s main.cpp
  * Obmedzenia formátu
  * Podpora mimo Arduino IDE

4. Štruktúra projektu PlatformIO
  * Vygenerovanie projektu cez CLI a GUI
  * Popis adresárovej štruktúry
  * platformio.ini (Project Configuration File)

5. Správa závislostí v Arduino IDE (správa knižníc a dosiek)
  * Závislosti sú inštalované globálne (\~/Arduino/Libraries)
    * Iba jedna verzia knižnica v systéme spoločná pre všetky projekty
  * Závislosti sa inštalujú ručne
    * Používateľ stiahne zip súbor
    * Používateľ použije správcu knižníc
  * Arduino Sketch neobsahuje informácie o závislostiach (zoznam knižníc a ich verzií)
    * Používateľ musí ručne nainštalovať knižnice a nainštalovať správne verzie knižníc
  * Arduino ekosystém a problém forkov
    * Pôvodný autor prestane knižnicu vyvíjať a nezačleňuje pull requesty
    * Vznikajú forky knižníc (desiatky až stovky), každý má svoju verziu knižnice
    * Knižnica dostupná v správcovi knižníc nemusí byť pre vás vhodná
    * Arduino Sketch nemá informáciu akú verziu knižnice (originál alebo fork) sme použili
  * Arduino Library Manager vs. PlatformIO Registry
    * PlatformIO registry si stráži kompatibilitu knižnice s cieľovou platformou
    * Popis Manifestu a integrácie knižnice do PlatformIO registry
    * Možnosť špecifikovať závislosť ako priamy odkaz na Git repozitár, takže presne vieme akú knižnicu použiť

6. Multiplatformnosť
  * Arduino IDE (Java, poskytuje verziu pre Windows, macOS, Linux, ARM 32/64bit) vs. PlatformIO (Python)
  * Python 2.7 a port PlatformIO na Python 3, žiadny platformovo špecifický kód

7. Vývoj pre viacero platforiem
 * Obmedzená podpora embedded dosiek v Arduino IDE, len pre Arduino platformu
   * Profil pre dosku sa inštaluje globálne. Rovnakú verziu používame v každom projekte.
 * Cross-kompilácia
 * Ako funguje podpora pre embedded platformy a dosky v PlatformIO
   * Toolchain predkompilovaný pre viacero platforiem
   * Tam, kde je to možné, sa stiahne platformovo nezávislý zdrojový kód
   * Pridanie novej platformy alebo dosky je jednoduché (ukázať github pre atmelavr)
   * Možnosť špecifikovať verziu toolchainu a frameworku pre projekt

8. Podpora viacerých cieľových prostredí v PlatformIO
  * platformio.ini a cielenie kódu pre viacero dosiek a prostredí

9. PlatformIO Plus
  * PlatformIO vs. PlatformIO Plus
  * Biznis model
  * Aké funkcie sú dostupné len v platenom balíku

9. Ladenie (debuggovanie)
  * Podpora debuggovania v IDE
  * Softvérové debuggovanie a obmedzenia
  * Hardvérové debuggery a PlatformIO
  * PIO Unified Debugger (PIO Plus)

10. Remote Agent (PIO Plus)
  * Vývoj na hardvéri, ktorý nie je priamo pripojený k počítaču
  * Vzdialená plocha vs. PlatformIO Remote Agent

11. Spolupráca v tíme
  * PlatformIO: Rýchle rozbehanie projektu
  * Možnosť vyvíjať v cloudovom IDE a kompilovať na vzdialenom agentovi (PIO Plus)

12. Testovanie
  * Prečo je dôležité testovať - kvalitný kód, rýchle aktualizácie, spokojný zákazník
  * Manuálne testovanie vs. automatizované testy
  * PlatformIO testovací framework
  * Alternatívne testovacie prostredie ArduinoUnit a podpora v PlatformIO

13. Continuous Integration a Delivery
  * Spúšťanie automatizovaných testov po každom commite
  * Zbieranie artefaktov z každého buildu - skompilované binárky pre embedded dosky

8. Dokumentácia
  * Arduino a dokumentácia písaná komunitou
  * PlatformIO a veľmi podrobná dokumentácia písaná autormi
  * Množstvo príkladov na ich webstránke
  * Doxygen a automatické generovanie dokumentácie z kódu

### Záver