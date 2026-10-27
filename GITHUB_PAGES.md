# Veröffentlichung mit GitHub Pages (Konto: pywelten)

Die Webseite kann bei GitHub Pages **ohne Build-Prozess** veröffentlicht werden. Alle Dateien müssen auf dem GitHub-Repository im Hauptverzeichnis liegen.

## Einmalig einrichten

1. https://github.com/new aufrufen.
2. Als Repository-Name `crimson-desert-bestiarium` eingeben.
3. **Public** auswählen (für GitHub Pages mit kostenlosem GitHub-Konto).
4. **Create repository** anklicken. Ein leeres Repository ist ausreichend; eine README ist nicht erforderlich.
5. Die bereitgestellte ZIP **auf dem PC entpacken**.
6. Im neuen Repository auf **Add file → Upload files** gehen.
7. **Den Inhalt** des entpackten Ordners hochladen (index.html, app.js, data.js, styles.css, monster-daten.json, assets-Ordner, Dokumentation). Wichtig: `index.html` muss im obersten Verzeichnis liegen – nicht in einem zusätzlichen Unterordner `crimson-desert-bestiarium`.
8. Mit **Commit changes** bestätigen.
9. **Settings → Pages → Build and deployment** öffnen.
10. Als Source **Deploy from a branch**, dann Branch **main** und Ordner **/(root)** auswählen und **Save** anklicken.
11. Nach der Veröffentlichung die Adresse öffnen:

    https://pywelten.github.io/crimson-desert-bestiarium/

GitHub veröffentlicht Änderungen normalerweise innerhalb weniger Minuten; laut GitHub kann es bis zu zehn Minuten dauern. Der Link ist erst nach erfolgreich aktiviertem GitHub Pages live.

## Später aktualisieren

Bearbeitete `data.js`-, `monster-daten.json`-, `app.js`-, CSS- und Bilddateien im Repository ersetzen. GitHub Pages veröffentlicht danach neu. Die persönliche Sammlung der Besucher wird dabei **nicht** geändert, da sie nur im jeweiligen Browser gespeichert ist.

## Privatsphäre und Domainwechsel

Die persönlichen Monsterfortschritte werden als `localStorage` je Browser und Domain gesichert. Daher bitte **vor einem Wechsel von file:// zu GitHub Pages die Sammlung als JSON exportieren** und auf der veröffentlichten Website wieder importieren.

Dies ist ein inoffizielles Fanprojekt. Bitte nur Medien verwenden, für die die Veröffentlichungsrechte vorliegen.

**Hinweis zum Projektstand:** Das Repository wurde während der Erstellung dieser ZIP noch **nicht** angelegt; eine live geschaltete GitHub-Seite wird nicht behauptet.

Offizielle Anleitungen:
- https://docs.github.com/en/pages/getting-started-with-github-pages/creating-a-github-pages-site
- https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site