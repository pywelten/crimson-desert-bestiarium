# PYWEL · Das Bestiarium

**Inoffizielles, unabhängiges, nicht-kommerzielles deutschsprachiges Crimson-Desert-Fanprojekt**, Stand **27. Oktober 2026**, redaktionelle Ausgabe **1.1**. **Keine Verbindung zu, Förderung durch oder Freigabe von Pearl Abyss.**

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

Crimson Desert und die zugehörigen Namen sind Marken bzw. geistiges Eigentum ihrer Rechteinhaber (Pearl Abyss). Dieses eigenständige Fanprojekt ist **nicht offiziell** und steht **in keiner Verbindung zu Pearl Abyss**. Das generierte Titelbild und die gezeichneten Symbole sind eigenständige Illustrationen. Zwei weitere, ausdrücklich als offiziell gekennzeichnete Spielimpressionen werden vom Pearl-Abyss-CDN geladen und sind geistiges Eigentum von Pearl Abyss; sie sind nicht im ZIP enthalten. Externe Texte wurden redaktionell zusammengefasst, nicht vollständig kopiert. Informationen können sich nach Spielupdates verändern.

Der hier entwickelte HTML/CSS/JavaScript-Projektcode darf privat verändert und für diese Fan-Website eigenständig gehostet werden. Für Inhalte und fremde Quellen gelten weiterhin die Rechte der jeweiligen Urheber.


## Fan-Content, Mediennutzung und Hinweise für Betreiber (Ausgabe 1.1)

Diese Seite ist **kostenlos, nicht-kommerziell, unabhängig und nicht offiziell**. Die sichtbare Kennzeichnung befindet sich im Seitenkopf, in der Navigation, im Footer und unter **Über & Rechtliches**. Der Hinweis genügt **nicht allein**, wenn die übrigen Fan-Content-Richtlinien verletzt würden.

- Offizielle Bildquellen: https://crimsondesert.pearlabyss.com/en-us/Media und die Richtlinien https://crimsondesert.pearlabyss.com/de-de/Policy?_policyNo=130; Angaben zu Bildrechten sind pro Foto in der Website sichtbar.
- Die extern geladenen Bilder sind allgemeine Spielimpressionen, **keine geprüften Einzelmonster-Fotos**. Freigegebene offizielle Screenshots sollten künftig pro Gegner nur bei belegter Identität zugeordnet werden.
- Für eine **öffentlich betriebene Webseite in Deutschland** können zusätzlich eigene Anforderungen an Impressum und Datenschutzhinweise bestehen. Diese Dokumente benötigen gegebenenfalls echte Betreiberangaben und sind nicht durch einen Urheberrechts-Disclaimer ersetzt. Der Betreiber sollte das eigenständig klären, bevor er die Seite langfristig öffentlich betreibt.
- Extern geladene Bilder übertragen beim Aufruf technisch Verbindungsdaten an den jeweiligen Bildhost. Ohne Internet werden die Fotos nicht angezeigt; alle Lexikonfunktionen und Kategorie-Illustrationen bleiben nutzbar.
- Ergänzt in Ausgabe 1.1: vierzehn Einträge mit besser belegten Kampf- oder Patchdaten, Boss-Revanche mit offiziellen Regeln und eine eigenständige Quellen-/Rechteseite.


## Ausgabe 1.2 – Bossbilder & Bildquellen (27.10.2026)

Neue [interaktive Bossbild-Galerie](bilder.html) mit Such- und Statusfilter, Spoilerschutz, direkten offiziellen Bossvideo-Links und Einzelquellen. Für 10 priorisierte Bosse liegt die geprüft dokumentierte Zuordnung unter [BILDER_TOP10.md](BILDER_TOP10.md) und maschinenlesbar in `bildquellen-top10.json`. `boss-bilder.js` lädt dieselben Daten in die Web-App. Das Originalbild von Weißhorn stammt vom offiziellen Pearl-Abyss-Bildserver. Vier weitere Einträge zeigen **ausdrücklich als Videovorschau gekennzeichnete** Bilder ihrer vom offiziellen Crimson-Desert-Kanal veröffentlichten Bossvideos. Bei fünf Gegnern wird kein unberechtigt übernommenes Einzelbild eingebunden. Die Standardbilder fallen bei blockierten externen Bildservern auf lokale Kategorie-Illustrationen zurück. Das Foto und die Videovorschauen sind unter den Fan-Content-Bedingungen eingebunden und keine frei lizenzierbaren Werke des Repositorys.

Die Galerie ist unter `https://pywelten.github.io/crimson-desert-bestiarium/bilder.html` vorgesehen, der Deploymentstatus wird separat geprüft.
