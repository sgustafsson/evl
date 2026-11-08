# evl

Englisch Vokabeln lernen

## trainer.html

Ein einfacher Vokabeltrainer als eigenständige HTML-Seite (Bootstrap 5 + jQuery). Die Oberfläche ist auf Deutsch.

### Vokabelliste

Die Vokabeln werden aus `vokabeln/liste.txt` geladen – eine Vokabel pro Zeile, leere Zeilen werden ignoriert. Jede Zeile enthält den englischen und den deutschen Begriff, getrennt durch ein Semikolon:

```
welcome to Brighton; Willkommen in Brighton
my name is; Mein Name ist
```

Fehlt das Semikolon, wird derselbe Text für beide Seiten verwendet.

### Übungsmodi

Über das Auswahlfeld **Übungsmodus** stehen zwei Modi zur Verfügung:

- **Tippen** – Der englische Begriff wird angezeigt, du tippst ihn ab. Die Eingabe wird Buchstabe für Buchstabe geprüft:
  - Passt die Eingabe bisher, bleibt das Feld neutral.
  - Ist die ganze Vokabel korrekt getippt, erscheint „Richtig!“ und nach kurzer Pause folgt automatisch die nächste.
  - Bei einem falschen Buchstaben wird das Feld rot markiert („Noch einmal versuchen.“).
  - Groß- und Kleinschreibung wird beim Prüfen ignoriert.
- **Übersetzen** – Eine Karteikarte zeigt den Begriff in der gewählten Ausgangssprache. Ein Klick auf die Karte dreht sie um und zeigt die Übersetzung. Mit **Zurück** und **Weiter** navigierst du durch die Vokabeln. Über das Feld **Richtung** wählst du:
  - **Englisch → Deutsch**
  - **Deutsch → Englisch**

### Weitere Einstellungen

- **Reihenfolge** – bestimmt die Reihenfolge der Vokabeln:
  - **Dateireihenfolge** – wie in `liste.txt` vorgegeben
  - **Alphabetisch** – nach dem englischen Begriff
  - **Zufällig** – pro Durchgang gemischt, ohne Wiederholungen
- **Anzahl Vokabeln** – wie viele Vokabeln ein Durchgang umfasst (1 bis zur Anzahl aller Zeilen; Standard: alle). Die Begrenzung wirkt nach dem Sortieren bzw. Mischen – „Zufällig“ mit Anzahl 10 ergibt also 10 zufällige Vokabeln.

Ein Zähler und ein Fortschrittsbalken zeigen den Lernfortschritt. Am Ende erscheint „Geschafft!“. Mit **Neu starten** beginnt der aktuelle Durchgang von vorn.

### Nutzung

Die Seite muss über einen Webserver geöffnet werden, da die Vokabelliste per AJAX geladen wird (beim direkten Öffnen über `file://` schlägt das Laden fehl). Zum Beispiel:

```bash
python -m http.server
```

Danach `http://localhost:8000/trainer.html` im Browser aufrufen.

Eigene Vokabeln einfach in `vokabeln/liste.txt` eintragen – eine pro Zeile im Format `englisch; deutsch`.
