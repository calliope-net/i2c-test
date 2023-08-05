### Calliope i2c Beispiel-Projekt mit vier i2c Modulen gleichzeitig
lädt alle i2c Erweiterungen von GitHub

> Diese Seite bei [https://calliope-net.github.io/i2c-test/](https://calliope-net.github.io/i2c-test/) öffnen

![](icon.png)

### Dieses Projekt importieren, mit Calliope testen, bearbeiten

Um dieses Repository in MakeCode zu importieren.

* öffne [https://makecode.calliope.cc](https://makecode.calliope.cc/)
* klicke auf **Importieren** und dann auf **Importiere URL**
* füge folgende **URL des Projekts** ein und klicke auf **Los geht's!**
* **https://github.com/calliope-net/i2c-test**

#### mit dem DIP Schalter wird eingestellt:

* Schalter 1 OFF: LCD Display zeigt Datum und Uhrzeit an (dauerhaft jede Sekunde)
  * solange Knopf B gedrückt: zeigt den Zustand der 6 DIP Schalter binär am LCD Display an
* Schalter 1 ON: aller 10 Sekunden wird eine Zeile auf die Speicherkarte protokolliert
  * Dateiname ergibt sich aus Datum/Zeit yyMMddHH.CSV (pro Stunde eine neue Datei)
  * Inhalt der Zeile: Dateiname; Datum; Zeit; DIP-Schalter binär; Temperatur; DrehungX; DrehungY; HardwareInterrupt; RGB
  * aktueller Dateiname und Zeit (aller 10 Sekunden wenn Zeile geschrieben) wird auf LCD Diaplay angezeigt
  * schreiben auf Speicherkarte kann zum Langzeit-Test der i2c Funktion genutzt werden
* Schalter 2 ON 3 OFF: LED-Matrix zeigt binär (in 5 Spalten) Uhrzeit (Stunde, Minute 10^1, Minute 10^0, Sekunde 10^1, Sekunde 10^0)
* Schalter 2 ON 3 ON: LED-Matrix zeigt binär Datum (Tag, -, Monat, -, Jahr)
* Schalter 2 OFF 3 ON: LED-Matrix löschen
* Schalter 4-5-6: Hintergrundfarbe, wenn ein Display mit 'Backlight' angeschlossen ist

> Einmalig Knopf A+B geklickt schaltet zusätzlich den Lagesensor (Drehung x- y-Achse) an, dieser hängt auch am i2c Bus.
> Danach werden im Sekundentakt die x und y Winkel im LCD Display rechts angezeigt (und auf Speicherkarte protokolliert).

> Der Sekundentakt kann von einer 'alle 1000 ms' Schleife kommen. Genauer geht es, wenn ein PIN mit CLK am RTC-Modul verdrahtet wird.
> Das wird erkennt und schaltet die Schleife ab. Ein Symbol wird links unten angezeigt.

> Auf dem LCD Display haben verschiedene Funktionen einen eigenen Bereich, ohne sich zu überschreiben.

im Projekt **calliope-net/i2c-test** sind auch noch fertige Blöcke unter **i2c Beispiele**

* braucht Erweiterungen LCD + LOG
  * leere LOG Dateien 'LOG00*.TXT' löschen und Protokoll-Datei schreiben, LCD Anzeige
  * Sonderzeichen in Datei 'UMLAUTE.TXT' schreiben und wieder lesen, LCD Anzeige
* braucht Erweiterungen LCD + RTC + LOG
  * Zeile auf Speicherkarte schreiben mit Datum und Zeit, Dateiname yyMMddHH.CSV (pro Stunde eine neue Datei), LCD Anzeige

#### 6 Erweiterungen werden automatisch mit geladen

* https://github.com/calliope-net/bit
* https://github.com/calliope-net/i2c
* https://github.com/calliope-net/dip-switch
* https://github.com/calliope-net/lcd16x2rgb
* https://github.com/calliope-net/log-qwiicopenlog
* https://github.com/calliope-net/rtc-pcf85063tp

![](blocks.png)

#### Metadaten (verwendet für Suche, Rendering)

* Calliope mini
* i2c
