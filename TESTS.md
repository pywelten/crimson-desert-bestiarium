# Qualitätssicherung (27. Oktober 2026)

## Erfolgreiche Prüfungen

- `node --check app.js` und `node --check data.js`: gültige JavaScript-Syntax.
- Browserbasierte Funktionstests mit Chromium/Playwright, wobei HTML, CSS und JavaScript **direkt in die Testseite eingebettet** wurden, da diese Umgebung lokale Datei-/HTTP-Navigation administrativ blockiert.
- Navigationsbereiche: Übersicht, Lexikon, Boss-Guide, Fundorte, Sammlung, Kampfsystem/PS5, Dateneditor, Quellen und Monsterdetailansicht.
- 117 Monstereinträge geladen und in der Lexikonansicht dargestellt.
- Volltextsuche ("Stone Worm") filtert die Liste.
- Favoriten-Klick auf Monsterkarte; Favoritenfilter und Entfernen aus gefilterter Liste.
- Storyspoiler-Schalter ist bedienbar.
- "Besiegt", "Wissen" und "Alle Belohnungen" werden korrekt ins lokale Fortschrittsobjekt geschrieben.
- Notizen und Besiegungszähler werden lokal geschrieben.
- JSON-Sicherung wurde durch echten Browser-Download erzeugt, Inhalt geprüft und über den Dateiupload wieder importiert.
- Benutzerdefinierter Monstereintrag wurde über das Editorformular erstellt und als Detailseite geöffnet.
- Mobilansicht bei 390 × 844 Pixel: Navigation funktioniert, kein horizontaler Dokumentüberlauf.
- Nach Korrektur von zwei Bedienungsfehlern (Favoriten-Button und Spoiler-Button) trat im Funktionstest kein unbehandelter JavaScript-Fehler auf.

## Grenzen dieser Prüfung

- Die Chromium-Testumgebung blockiert echte Seitenaufrufe per `file://` oder `localhost`; daher war der Test kein vollständiger End-to-End-Test einer tatsächlich veröffentlichten GitHub-Pages-URL.
- Die Wiederherstellung des Browserzustands wurde durch localStorage-Serialisierung und JSON-Import geprüft. Ein echter Browserverlauf mit Neustart auf der finalen Domain ist nach Veröffentlichung zusätzlich zu überprüfen.
- Nicht alle externen Quellen-URLs wurden einzeln live auf Erreichbarkeit geprüft.
- Aussagen zur Verfügbarkeit sämtlicher Kreaturen, Spawns und DLCs werden nicht als vollständig verifiziert ausgewiesen.

## Empfohlene letzte Kontrolle nach Veröffentlichung

1. Hauptseite und Titelbild laden.
2. Mobilansicht im echten Smartphone-Browser öffnen.
3. Ein Monster als besiegt markieren, Browser-Tab neu laden und Zustand prüfen.
4. JSON herunterladen und anschließend wieder importieren.
5. Storyspoiler und Filter testen.
6. Quellen-Links und die Druckansicht stichprobenartig öffnen.


## 27.10.2026 – Repository-Update 1.1

Per GitHub-Dateiabfrage kontrolliert: `index.html`, `app.js`, `data.js`, `styles.css`, `monster-daten.json` sind vorhanden. JavaScript-Syntax für `app.js` und `data.js` mit Syntaxparser geprüft; JSON mit **117 Einträgen** validiert. Datenblätter `monster-daten.json` und `data.js` im gleichen Release aktualisiert. Navigation und Routing um `#/rechtliches` ergänzt. Sichtbare Bildnachweise, Fan-Content-Links, zusätzlicher Boss-Revanche-Block (mit Spoilerschalter) und neue Quellen eingebaut.

**Nicht vollständig automatisiert geprüft:** Laufzeit-Rendering auf allen Smartphones, offizielle Pearl-Abyss-Hotlink-Bilder in jedem Endnutzerbrowser und veröffentlichte GitHub-Pages-URL. Die Bilder werden extern geladen. Nach Deploy bitte die Startseite und `#/rechtliches` im Browser öffnen sowie Console/Network-Fehler und Spoilerdarstellung prüfen. Die Prüfung ersetzt keine rechtliche Beratung zu Impressum und Datenschutz.
