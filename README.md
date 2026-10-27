# PYWEL · Das Bestiarium

**Inoffizielles deutschsprachiges Crimson-Desert-Fanprojekt**, Stand **27. Oktober 2026**.

Diese Ausgabe enthält **117 redaktionell zusammengestellte Datensätze aus zwölf Kategorien**. Sie umfasst insbesondere die bekannten Steinwürmer, Dornenranken, getarnten Pflanzen und Wandergolems, 23 legendäre Tiere, dokumentierte Haupt- und optionale Bosse sowie einige weitere Gegnertypen. Das ist eine **kuratierte, nicht vollständige Auswahl sämtlicher Kreaturen des Spiels**. Die externe Datenbank `crimsondesert.gaming.tools` umfasst wesentlich mehr Einträge. Für unklare Angaben werden ausdrücklich keine Positionen, Lootmengen oder Schwächen erfunden.

## Schnellstart

1. Gesamtes ZIP entpacken.
2. `index.html` in einem aktuellen Browser wie Edge, Chrome oder Firefox öffnen. Ein Webserver ist **nicht notwendig**. Bei strengen Browserrichtlinien funktioniert auch jeder lokale statische Webserver.
3. Einträge durchsuchen, Monster als besiegt markieren, Wissen und Beute abhaken, Favoriten und Notizen pflegen.
4. Im Menü **Meine Sammlung** regelmäßig mit **Gesamte Sammlung als JSON exportieren** eine Sicherungsdatei erstellen.

Keine Registrierung, Datenbank, kostenpflichtigen APIs, Builds, Node.js-Installation oder CDN-Abhängigkeiten. Die App verwendet klassisches HTML, CSS und JavaScript. Für das Öffnen verlinkter Quellen ist eine Internetverbindung nötig.

## Projektdateien

| Datei | Funktion |
| --- | --- |
| `index.html` | Navigationsgerüst und App-Einstieg |
| `styles.css` | Farben, Layout, Mobilansicht, Druckansicht |
| `data.js` | Lieferumfang der recherchierten Monster, vom Browser direkt geladen |
| `monster-daten.json` | Separat nutzbare Rohdaten |
| `app.js` | Filter, Guides, Fortschritt, Spoiler, Export/Import und Dateneditor |
| `assets/pywel-hero.png` | Eigenständig generiertes Fantasy-Titelbild |
| `assets/*.svg` | Eigenständig gezeichnete Kategorie-Illustrationen |
| `QUELLEN.md` | Recherchequellen, Zuverlässigkeit, Aktualitätsgrenzen |
| `TESTS.md` | Technische Prüfungen und bekannte Grenzen |
| `GITHUB_PAGES.md` | Anleitung zur Veröffentlichung unter dem Konto `pywelten` |

## Funktionsübersicht

- Übersicht, responsive Navigation, zwölf Monsterkategorien, Bossguide und Fundortübersicht
- Volltextsuche, kombinierbare Filter für Kategorie, Region, Schwierigkeit, Element, Schwäche, Gegnertyp, besiegt, Wissen und Favoriten
- Sortierung nach Name, Region und Schwierigkeit; Karten- und Listenansicht
- Eigene Detailseite je Datensatz mit englischem Originalnamen, deutschsprachigem Namen, Quellenstand, Fundort, Quest/Kapitel, Angriffen, Strategie, Schritten und Tastensymbolen
- Storyspoiler standardmäßig ausgeblendet
- „Besiegt“, „Wissen freigeschaltet“, „Alle Belohnungen“, Favorit, Besiegungszähler, Notizen
- Gesamtdashboard und Fortschritt je Kategorie und Region
- JSON-Backup und -Import einschließlich eigener Datensatzänderungen
- Eingebauter Editor für neue und bestehende Einträge, eigener Bildpfad möglich
- Gedruckter Monster-Guide mit vereinfachtem Drucklayout, Hell-/Dunkelmodus
- Quellen pro Eintrag, letzte redaktionelle Prüfung, Quellenverzeichnis, Änderungsübersicht

## Wo werden die Daten gespeichert?

Das Projekt nutzt `localStorage` unter dem Schlüssel `pywel-bestiary-v1` auf dem jeweiligen Browser und Ursprung (`file://`/Domain). Daten werden **nicht auf einen Server gesendet**. Ein Umzug auf eine andere Domain oder einen anderen Browser erfordert **JSON-Export und JSON-Import**. Private-Browsing-Fenster oder gesperrter Browser-Speicher können die dauerhafte Speicherung verhindern. Deshalb bitte regelmäßig eine Backup-Datei aufbewahren.

Eine Sicherung umfasst eigene und bearbeitete Monstereinträge, Fortschritt, Einstellungen und zuletzt angesehene Monster. Der Import überschreibt die bestehende lokale Sammlung nach Sicherheitsabfrage.

## Neue Kreaturen hinzufügen

Menü **Datenbank bearbeiten** → **+ Eintrag hinzufügen**. Pflichtfelder sind deutscher und englischer Name. Für vorhandene Gegner im Menü **Bearbeiten** verwenden. Bei nicht belegbaren Feldern **Unbekannt** eintragen und im Quellenfeld mindestens einen nachvollziehbaren Link hinterlegen. Die ursprünglichen Datensätze bleiben in `data.js` unverändert; deine Korrekturen werden als lokale Overlays gespeichert und in deine Sicherungsdatei aufgenommen.

Bilder sind standardmäßig originale Kategorie-Illustrationen. Für individuelle eigene Bilder eine Datei, z. B. `assets/mein-wurm.webp`, in den `assets/`-Ordner legen und im Editor das Feld **Optionaler Bildpfad** ausfüllen. Aus Sicherheitsgründen werden nur lokale Dateien im Ordner `assets` mit bekannten Bild-Endungen angenommen. **Nur Bilder verwenden, für die du die nötigen Rechte hast.** Bilder werden beim JSON-Backup nicht mitexportiert: Sie müssen beim Website-Umzug zusätzlich in den `assets`-Ordner übernommen werden.

Für dauerhafte gemeinsame Datenbankupdates kann `data.js` mit den validierten JSON-Datensätzen aus dem Menü **Datenbank exportieren** neu erzeugt werden: Datei enthält dann das kombinierte Endergebnis; den Inhalt unter `window.CD_ENTRIES = <Datensätze>;` übernehmen. Alternativ kann der veröffentlichte `monster-daten.json`-Bestand mit dem Projekt aktualisiert und `data.js` beim nächsten Release neu generiert werden.

## Fundorte und Weltkarte

Diese Version zeigt **funktionierende, filterbare Fundortlisten** mit Quellenlinks und führt zu einer externen Crimson-Desert-Karten-/Guide-Seite. Sie enthält keine selbst erfundenen Positionen. Der Zugriff auf verlässliche und unter freien Rechten redistribuierbare Koordinaten bzw. eine freie Karte war zum Entwicklungszeitpunkt nicht ausreichend geklärt. Ein vollwertiges lokal integriertes Ingame-Map-Tile-System ist daher **nicht enthalten**.

## DLC-Grenze / Chronologie

Pearl Abyss kündigte an, dass „Charting the Unknown“ am **29. Oktober 2026** erscheint. Am Datum dieses Projekts (27.10.2026) sind die vollständigen DLC-Kreaturen noch nicht verlässlich überprüfbar. Sie sind **nicht als bestätigte spielbare Monster** aufgenommen. Bitte nach Veröffentlichung anhand offizieller Patchnotes und mehrerer Quellen nachpflegen.

## Inhalte / Rechtliches

Crimson Desert und die zugehörigen Namen sind Marken bzw. geistiges Eigentum ihrer Rechteinhaber (Pearl Abyss). Dieses eigenständige Fanprojekt ist **nicht offiziell** und steht **in keiner Verbindung zu Pearl Abyss**. Das generierte Titelbild und die gezeichneten Symbole sind eigenständige Illustrationen ohne die Übernahme offizieller Logos und Screenshots. Externe Texte wurden redaktionell zusammengefasst, nicht vollständig kopiert. Informationen können sich nach Spielupdates verändern.

Der hier entwickelte HTML/CSS/JavaScript-Projektcode darf privat verändert und für diese Fan-Website eigenständig gehostet werden. Für Inhalte und fremde Quellen gelten weiterhin die Rechte der jeweiligen Urheber.
