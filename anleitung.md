# HTML-Lernprotokoll: Schritt-für-Schritt-Anleitung

Begonnen am 10. Okt. 2026 · @Michael

**Wichtige Links**

- Meine Webseite: https://michaelquehenberger.github.io/Annahof/
- Editor (iPad/Browser): https://vscode.dev/github/michaelquehenberger/Annahof/tree/main?vscode-lang=de-de
- Repository: https://github.com/michaelquehenberger/Annahof

**Inhalt**

- Teil A – Lernprotokoll (was ich gemacht habe, der Reihe nach)
- Teil B – So arbeite ich (jedes Mal)
- Teil C – HTML-Spickzettel
- Teil D – Fortschritt und nächste Schritte

---

# Teil A – Lernprotokoll

## Überblick: Code-Bereich oder normaler Chat?

Der Code-Bereich in Claude ist für Programmierarbeit an echten Projektdateien gedacht, der normale Chat (oder ein Projekt) für Erklären, Planen und Lernen. Für den Einstieg in HTML nutze ich beides: den Chat zum Verstehen, den Code-Bereich, wenn Claude Dateien in meinem GitHub-Repository lesen, anlegen oder prüfen soll.

|  | Normaler Chat / Projekt | Code-Bereich |
| --- | --- | --- |
| Wofür | Erklären, Unterrichtsplanung, Fragen zu Fehlern, Skriptum/Buch als PDF hinterlegen | Dateien lesen, anlegen und ändern, Code prüfen, committen |
| Braucht ein Repository | Nein | Ja (sonst: „Ein Repository muss ausgewählt werden“) |
| Beispiel | „Erkläre mir `<ul>` und `<li>`“ | „Lege eine Übungsseite im Ordner `uebungen` an“ |

**Tipp zum Lernen:** Dazuschreiben, wie Claude arbeiten soll, zum Beispiel: „Ich möchte HTML selbst lernen. Erkläre Schritt für Schritt und gib mir kleine Übungen.“

**Diese Dokumentation** liegt direkt im Repository (`anleitung.md`). So ist sie neben dem Code, auf GitHub lesbar und Claude kann sie im Code-Bereich lesen und ergänzen.

## Schritt 1: GitHub-Repository anlegen und mit Claude verbinden

GitHub ist ein Online-Speicher für Code-Projekte. Ein Repository ist darin ein Projektordner. Mein Repository heißt **Annahof**.

1. Auf github.com ein kostenloses Konto anlegen (das muss ich selbst tun).
2. Oben rechts auf „+“ tippen, dann „New repository“. Name vergeben, Haken bei „Add a README“ setzen.
3. In Claude im Code-Bereich auf „Repository hinzufügen“ tippen und GitHub mit Claude verknüpfen. Die Freigabe auf der GitHub-Seite bestätigen.
4. Das Repository auswählen. Danach kann die Sitzung starten.

**Woran ich erkenne, dass es geklappt hat:** Im Titel der Sitzung steht der Repository-Name („Annahof“), und es läuft eine Meldung „Sitzung initialisiert“.

Claude hat dann die Startstruktur angelegt: `index.html`, `uebungen/01-erste-seite/index.html`, `bilder/`, `README.md`.

## Schritt 2: vscode.dev am iPad, Repository öffnen, Branch verstehen

VSCodium und VS Code gibt es nicht als iPad-App. Am iPad nutze ich VS Code im Browser (Safari). Am Schulrechner arbeite ich mit VSCodium – beides ist im Kern derselbe Editor.

1. In Safari **vscode.dev** öffnen (alternativ im Repository auf github.com die Taste `.` drücken oder `github.com` durch `github.dev` ersetzen). Am schnellsten: den Editor-Link oben verwenden.
2. Links im Explorer auf **„Open Remote Repository“** tippen.
3. **„Open Repository from GitHub“** wählen, GitHub-Zugriff erlauben und das Repository **Annahof** auswählen.
4. Im Explorer erscheinen `bilder`, `uebungen`, `index.html` und `README.md`.

**Branch:** Ein Branch (Zweig) ist ein eigener Arbeitsstand. Welcher gerade aktiv ist, steht **unten links in der Statusleiste**. Am Anfang stand dort `claude/html-basics-vscodium-zio2y2` – der Zweig, auf dem die Claude-Sitzung ihre Dateien abgelegt hat. Mein Hauptzweig ist jetzt **`main`** (siehe Schritt 6). Arbeit von einem anderen Zweig übernimmt man auf GitHub über einen **Pull Request**.

**Einschränkung:** Im Browser-Editor gibt es kein Live Server und kein Terminal. Die Vorschau am iPad läuft über GitHub Pages (Schritt 5).

## Schritt 3: Aufbau von index.html Zeile für Zeile

Eine HTML-Seite besteht aus einem Kopf (`head`, unsichtbare Infos) und einem Körper (`body`, alles Sichtbare). Fast jeder Tag wird geöffnet (`<p>`) und wieder geschlossen (`</p>`).

| Zeilen | Tag | Bedeutung |
| --- | --- | --- |
| 1 | `<!DOCTYPE html>` | Sagt dem Browser: modernes HTML |
| 2 | `<html lang="de">` | Umschließt alles, Sprache Deutsch |
| 3-7 | `<head>` | Infos über die Seite: `charset="UTF-8"` (Umlaute), `viewport` (Handy-Anpassung), `<title>` (Text im Browser-Tab) |
| 8-21 | `<body>` | Alles, was man auf der Seite sieht |
| 9 | `<!-- ... -->` | Kommentar, im Browser unsichtbar |
| 10 | `<h1>` | Hauptüberschrift |
| 11 | `<p>` | Absatz |
| 13 | `<h2>` | Unterüberschrift |
| 14-18 | `<ul>` mit `<li>` | Aufzählung, jeder Punkt in einem `<li>` |
| 20 | `<a href="...">` | Link, der Pfad in `href` zeigt auf die Zieldatei |

**Besonderheit:** In den Zeilen 15-17 stehen `&lt;` und `&gt;`. Das sind Ersatzzeichen für `<` und `>`, damit der Browser sie als Text anzeigt und nicht als Tag.

## Schritt 4: Mini-Übung 1 und Änderungen speichern

**Übung (5 Minuten):**

- [x] In `index.html` Zeile 10 den Text der Überschrift ändern (zum Beispiel `Hallo MQ Welt!`).
- [ ] Nach Zeile 11 einen neuen Absatz einfügen: `<p>Ich lerne gerade HTML.</p>`
- [ ] In der Liste einen vierten Punkt ergänzen: `<li>Links mit <code>&lt;a&gt;</code></li>`
- [ ] Denkaufgabe: Was passiert, wenn bei einem `<li>` das `</li>` fehlt? Fehleranzeige unten (Zahlen neben dem Warndreieck) beobachten.

**Änderungen speichern (Commit und Push):**

1. Links auf das Symbol **Quellcodeverwaltung** (Verzweigungs-Symbol) tippen. Geänderte Dateien stehen unter „Änderungen“, markiert mit **M**.
2. In das Feld **„Nachricht“** eine kurze Notiz tippen, zum Beispiel `Überschrift geändert`. Ohne Nachricht erscheint der rote Hinweis „Sie müssen vor dem Committen eine Commitnachricht angeben“.
3. Auf den blauen Button **„Commit und Push“** tippen. Falls eine Rückfrage erscheint, bestätigen.
4. Erfolg: Unter „Änderungen“ steht nichts mehr.

## Schritt 5: Vorschau am iPad mit GitHub Pages

**Status:** erledigt ✅. GitHub Pages ist bei kostenlosen GitHub-Konten nur für **öffentliche** Repositories verfügbar – deshalb ist „Annahof“ jetzt öffentlich.

1. Auf github.com das Repository **Annahof** öffnen, dann **Settings**.
2. Unter **General** ganz unten bei **Danger Zone** auf „Change visibility“ tippen und **Public** wählen.
3. In den Settings links auf **Pages** gehen.
4. Bei „Source“ **Deploy from a branch** wählen. Als Branch **`main`** und den Ordner **`/ (root)`** wählen, dann **Save**.
5. Nach etwa einer Minute ist die Seite unter `https://michaelquehenberger.github.io/Annahof/` erreichbar. Nach jedem Commit dauert es kurz, bis die Änderung sichtbar ist (ggf. zweimal neu laden).

> ⚠️ **Nicht anklicken:** „Upgrade“, „Start free for 30 days“, „GitHub Enterprise“ und „Configure“ bei Jekyll/Static HTML – alles unnötig bzw. kostenpflichtig. Steht bei Source plötzlich „GitHub Actions“, zurück auf **Deploy from a branch** stellen.

**Wichtig:** Ein öffentliches Repository ist für alle sichtbar. Keine Schülerdaten und nichts Privates ablegen.

**Alternative (Repository bleibt privat):** Als Lehrer über https://education.github.com/teachers GitHub Pro gratis beantragen – dann geht Pages auch privat. Sonst: keine Browser-Vorschau am iPad; in der Schule zeigt VSCodium mit Live Server die Vorschau.

## Schritt 6: Hauptzweig `main` einrichten

**Status:** teilweise erledigt.

1. [x] In vscode.dev unten links auf den Branch-Namen tippen → **„+ Neuen Branch erstellen…“** → `main` eingeben → Enter. Unten links steht jetzt `main`.
2. [ ] Auf GitHub: **Settings → General → Default branch** → Pfeil-Symbol → `main` → **Update**.
   Warum wichtig: Solange der Default noch der `claude/…`-Zweig ist, landen Änderungen, die ich direkt auf github.com mache, dort statt auf `main` – und erscheinen nicht auf meiner Webseite.
3. [ ] Den `claude/…`-Zweig per Pull Request in `main` übernehmen (Claude kann den Pull Request anlegen, ich bestätige mit **Merge**).

**Ab jetzt:** Vor dem Arbeiten unten links prüfen, dass `main` steht.

## Schritt 7: Übung 1 – Liste mit Hobbys

Datei: `uebungen/01-erste-seite/index.html` (im Explorer: `uebungen` → `01-erste-seite` → `index.html`). Beide Dateien heißen `index.html` – welche offen ist, zeigt die Pfadzeile über dem Code.

```html
<h2>Meine Hobbys</h2>
<ul>
  <li><strong>Sport</strong></li>
  <li>Kochen</li>
  <li>Natur</li>
</ul>
```

- `<ul>` = Rahmen der Liste, jedes `<li>` = ein Punkt.
- `<strong>` steht **innerhalb** des `<li>` – richtig verschachtelt.
- Feedback: Rechtschreibung laut Duden „Hobby**s**“; Einrückung mit Rechtsklick → **Dokument formatieren** korrigieren.

---

# Teil B – So arbeite ich (jedes Mal)

### Am iPad – vscode.dev
1. Editor-Link öffnen.
2. **Unten links prüfen: steht dort `main`?** Wenn nicht → antippen und `main` wählen.
3. Datei im **Explorer** öffnen und bearbeiten.
4. Quellcodeverwaltung → Nachricht → **Commit und Push**.
5. Ca. 1 Minute warten → Tab mit meiner Webseite **neu laden**.

> ⚠️ Änderungen in vscode.dev liegen nur im Browser, bis ich committe. Am Ende jeder Arbeitsphase **immer committen**!

### Am PC – VSCodium
1. **Datei → Ordner öffnen** → Projektordner wählen.
2. **Zuerst synchronisieren** (holt die Änderungen vom iPad).
3. Bearbeiten, Vorschau mit **Live Server**: Rechtsklick auf die HTML-Datei → *Open with Live Server*.
4. Quellcodeverwaltung → Nachricht → **Commit** → **Änderungen synchronisieren**.

| | VSCodium (PC) | vscode.dev (iPad) |
|---|---|---|
| Hochladen | Commit, dann Synchronisieren | Commit und Push (ein Schritt) |
| Vorschau | Live Server | Meine Webseite neu laden |
| Terminal | ✅ | ❌ |

### Nützliche Tricks
- `!` + **Tab** in leerer HTML-Datei → komplettes Grundgerüst
- `ul>li*3` + **Tab** → Liste mit 3 Punkten (nur mit echter Tastatur)
- Rechtsklick im Code → **Dokument formatieren** → Einrückung automatisch
- Statusleiste unten: ⓧ 0 ⚠ 0 = keine Fehler
- Externe Tastatur am iPad erleichtert `<`, `>`, `/`, `"` enorm

---

# Teil C – HTML-Spickzettel

### Grundgerüst – jede Seite
```html
<!DOCTYPE html>
<html lang="de">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Seitentitel</title>
</head>
<body>
  Sichtbarer Inhalt
</body>
</html>
```

### Gelernte Tags

| Tag | Bedeutung | Beispiel |
|---|---|---|
| `<h1>`–`<h6>` | Überschriften (1 = größte) | `<h1>Über mich</h1>` |
| `<p>` | Absatz | `<p>Ich heiße …</p>` |
| `<!-- -->` | Kommentar (unsichtbar) | `<!-- Notiz -->` |
| `<ul>` | Aufzählung mit Punkten | siehe Schritt 7 |
| `<ol>` | nummerierte Liste | wie `<ul>`, nur mit Zahlen |
| `<li>` | ein Listenpunkt | `<li>Kochen</li>` |
| `<strong>` | fett / wichtig | `<strong>Sport</strong>` |
| `<a href="…">` | Link | `<a href="https://www.orf.at">ORF</a>` |
| `<code>` | Code-Schrift | `<code>&lt;p&gt;</code>` |

### Links
- **Externe Seite:** volle Adresse mit `https://` → `<a href="https://www.orf.at">ORF</a>`
- **Eigene Seite:** relativer Pfad → `<a href="uebungen/01-erste-seite/index.html">Übung 1</a>`
- `../` heißt „einen Ordner nach oben“ → `<a href="../../index.html">Zurück</a>`

### Regeln
- Jedes geöffnete Tag wird geschlossen: `<p>` … `</p>` (Ausnahmen: `<br>`, `<img>`, `<meta>`)
- Richtig verschachteln: `<li><strong>…</strong></li>` ✅ – nicht `<li><strong>…</li></strong>` ❌
- Dateinamen klein, ohne Leerzeichen und Umlaute: `ueber-mich.html`
- `&lt;` und `&gt;` zeigen `<` und `>` als Text an

---

# Teil D – Fortschritt und nächste Schritte

### Übung 1 – Über mich (`uebungen/01-erste-seite/index.html`)
- [x] Überschrift `<h2>` für die Hobbys
- [x] Liste mit Hobbys (`<ul>`, `<li>`)
- [x] Ein Hobby fett mit `<strong>`
- [ ] Absatz über mich (`<p>`)
- [ ] Link zu meiner Lieblingsseite (`<a href="…">`)

### Als Nächstes
- [ ] Bilder einbinden: `<img src="../../bilder/foto.jpg" alt="Beschreibung">`
- [ ] Tabellen: `<table>`, `<tr>`, `<td>`, `<th>`
- [ ] Seitenaufbau: `<header>`, `<nav>`, `<main>`, `<footer>`
- [ ] Danach **CSS**: eigene Datei `style.css`, eingebunden mit `<link rel="stylesheet" href="style.css">` – Farben, Schrift, Layout

---

## Notizen

*(Platz für eigene Notizen, Fragen, Aha-Momente – Kästchen abhaken: `- [ ]` → `- [x]`)*

-
