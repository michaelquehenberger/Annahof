# HTML-Lernprotokoll: Schritt-für-Schritt-Anleitung

Begonnen am 10. Okt. 2026 · @Michael

**Wichtige Links**

- Meine Webseite: https://michaelquehenberger.github.io/Annahof/
- Editor (iPad/Browser): https://vscode.dev/github/michaelquehenberger/Annahof/tree/main?vscode-lang=de-de
- Repository: https://github.com/michaelquehenberger/Annahof

**So ist dieses Protokoll aufgebaut:** Die Schritte stehen in der Reihenfolge, in der ich arbeite. Jeder Schritt hat einen Status, eine Anleitung und eine Erfolgskontrolle („Woran ich erkenne, dass es geklappt hat“). Erledigtes hake ich ab: `- [ ]` → `- [x]`.

| Nr. | Schritt | Status |
| --- | --- | --- |
| 1 | GitHub-Repository anlegen und mit Claude verbinden | ✅ |
| 2 | vscode.dev am iPad öffnen | ✅ |
| 3 | Aufbau von index.html verstehen | ✅ |
| 4 | Erste Änderung und Commit und Push | ✅ |
| 5 | Repository öffentlich machen | ✅ |
| 6 | Branch `main` anlegen | ✅ |
| 7 | GitHub Pages einschalten | ✅ |
| 8 | Übung 1a: Liste mit Hobbys | ✅ |
| 9 | Default branch auf `main` stellen | ✅ |
| 10 | Claudes Änderungen per Pull Request übernehmen | ✅ |
| 11 | Übung 1b: Absatz und Link | ⏳ als Nächstes |
| 12 | Bilder | ⬜ |
| 13 | Tabellen | ⬜ |
| 14 | Seitenaufbau | ⬜ |
| 15 | CSS | ⬜ |

Direkt danach: **Grundregeln für Ordnerstruktur und Dateinamen**. Am Ende: **Täglicher Arbeitsablauf** (inkl. Pull Requests und Git-Wörterbuch) und **HTML-Spickzettel** zum Nachschlagen.

---

## Grundregeln: Ordnerstruktur und Dateinamen

Diese Regeln gelten für das ganze Projekt. Ich lege sie einmal fest und halte mich immer daran – wer später umbenennt oder verschiebt, macht Links kaputt.

### Meine Ordnerstruktur

```
Annahof/
├── index.html              Startseite = Inhaltsverzeichnis aller Übungen
├── README.md               kurze Projektbeschreibung (für GitHub)
├── anleitung.md            dieses Lernprotokoll
├── doku/                   Dokumentation, z. B. vscodium-manual.md (Manual für den Unterricht)
├── css/                    später: style.css (gilt für alle Seiten)
├── bilder/                 Bilder, die mehrere Seiten nutzen
└── uebungen/
    ├── 01-erste-seite/
    │   └── index.html
    ├── 02-bilder/
    │   ├── index.html
    │   └── bilder/         nur Bilder dieser einen Übung
    ├── 03-tabellen/
    │   └── index.html
    └── 04-seitenaufbau/
        └── index.html
```

### Die 6 Regeln

1. **`index.html` ist die Standardseite eines Ordners.** Ruft man einen Ordner im Browser auf, zeigt der Server automatisch dessen `index.html`:
   - `…/Annahof/` → `index.html` im Hauptordner (Startseite)
   - `…/Annahof/uebungen/01-erste-seite/` → `index.html` in diesem Ordner

   Die Startseite heißt also **immer** `index.html` und liegt ganz oben.
2. **Dateinamen klein, ohne Leerzeichen, Umlaute und Sonderzeichen.** Wörter mit Bindestrich verbinden.
   - ✅ `ueber-mich.html`, `foto-skifahren.jpg`
   - ❌ `Über Mich.html`, `Foto 1.JPG`

   Webserver unterscheiden Groß-/Kleinschreibung: `Foto.jpg` und `foto.jpg` sind zwei verschiedene Dateien.
3. **Jede Dateiart in ihren Ordner:** Bilder → `bilder/`, CSS → `css/`. HTML-Seiten dorthin, wo sie inhaltlich hingehören.
4. **Ein Ordner pro Übung, nummeriert mit führender Null:** `01-…`, `02-…`, … `10-…` – so stimmt die Reihenfolge im Explorer (ohne Null käme `10` vor `2`).
5. **Nur relative Pfade:** `href="uebungen/01-erste-seite/"` statt voller Adresse. So funktioniert die Seite überall gleich – Live Server, iPad, GitHub Pages.
   - `bilder/foto.jpg` → Ordner `bilder` im selben Ordner
   - `../` → einen Ordner nach oben
   - `../../css/style.css` → zwei Ordner nach oben, dann in `css`
6. **Struktur früh festlegen, dann nicht mehr ändern.** Umbenennen oder Verschieben macht alle Links darauf kaputt.

### Die Startseite als Inhaltsverzeichnis

`index.html` im Hauptordner verlinkt auf jede Übung. Bei jeder neuen Übung kommt ein Listenpunkt dazu:

```html
<h2>Meine Übungen</h2>
<ul>
  <li><a href="uebungen/01-erste-seite/">Übung 1: Über mich</a></li>
  <li><a href="uebungen/02-bilder/">Übung 2: Bilder</a></li>
</ul>
```

Jede Übungsseite hat unten einen Link zurück: `<a href="../../">Zurück zur Startseite</a>`

### Neue Übung anlegen (in vscode.dev)

1. Im Explorer auf den Ordner `uebungen` tippen, dann oben auf das Symbol **Neuer Ordner** (Ordner mit „+“) → Name z. B. `02-bilder`.
2. Den neuen Ordner antippen, dann **Neue Datei** (Blatt mit „+“) → `index.html`.
3. In der leeren Datei `!` + **Tab** → Grundgerüst. `lang="de"` und den `<title>` anpassen.
4. In der Startseite `index.html` einen Link auf die neue Übung ergänzen.
5. **Commit und Push.**

> ℹ️ **Leere Ordner speichert Git nicht.** Ein Ordner wird erst hochgeladen, wenn eine Datei darin liegt. Deshalb steckt in `bilder/` die unsichtbare Platzhalterdatei `.gitkeep`.

---

## Vorab: Code-Bereich oder normaler Chat?

Der Code-Bereich in Claude ist für Programmierarbeit an echten Projektdateien gedacht, der normale Chat (oder ein Projekt) für Erklären, Planen und Lernen.

|  | Normaler Chat / Projekt | Code-Bereich |
| --- | --- | --- |
| Wofür | Erklären, Unterrichtsplanung, Fragen, Skriptum/Buch als PDF hinterlegen | Dateien lesen, anlegen und ändern, Code prüfen, committen |
| Braucht ein Repository | Nein | Ja (sonst: „Ein Repository muss ausgewählt werden“) |
| Beispiel | „Erkläre mir `<ul>` und `<li>`“ | „Lege eine Übungsseite im Ordner `uebungen` an“ |

**Tipp:** Dazuschreiben, wie Claude arbeiten soll, z. B. „Ich möchte HTML selbst lernen. Erkläre Schritt für Schritt und gib mir kleine Übungen.“

Dieses Protokoll liegt im Repository (`anleitung.md`) – Claude kann es im Code-Bereich lesen und ergänzen.

---

## Schritt 1: GitHub-Repository anlegen und mit Claude verbinden ✅

GitHub ist ein Online-Speicher für Code-Projekte. Ein Repository ist darin ein Projektordner. Mein Repository heißt **Annahof**.

- [x] Auf github.com ein kostenloses Konto anlegen (das muss ich selbst tun).
- [x] Oben rechts auf „+“ → „New repository“. Name vergeben, Haken bei „Add a README“ setzen.
- [x] In Claude im Code-Bereich auf „Repository hinzufügen“ tippen und GitHub mit Claude verknüpfen. Freigabe auf der GitHub-Seite bestätigen.
- [x] Das Repository auswählen, Sitzung starten.

**Woran ich erkenne, dass es geklappt hat:** Im Titel der Sitzung steht „Annahof“, und es läuft „Sitzung initialisiert“. Claude hat die Startstruktur angelegt: `index.html`, `uebungen/01-erste-seite/index.html`, `bilder/`, `README.md`.

## Schritt 2: vscode.dev am iPad öffnen ✅

VSCodium gibt es nicht als iPad-App. Am iPad nutze ich VS Code im Browser (Safari) – im Kern derselbe Editor. Am Schulrechner arbeite ich mit VSCodium.

- [x] In Safari den **Editor-Link** (oben) öffnen. Alternativ: im Repository auf github.com die Taste `.` drücken.
- [x] Oder über vscode.dev: Explorer → **„Open Remote Repository“** → **„Open Repository from GitHub“** → Zugriff erlauben → **Annahof**.

**Woran ich erkenne, dass es geklappt hat:** Links im Explorer stehen `bilder`, `uebungen`, `index.html`, `README.md`.

**Was ein Branch ist:** Ein Branch (Zweig) ist ein eigener Arbeitsstand. Welcher aktiv ist, steht **unten links in der Statusleiste**. Mein Hauptzweig ist `main` (Schritt 6). Claude arbeitet auf einem eigenen Zweig (`claude/html-basics-vscodium-zio2y2`); seine Änderungen übernehme ich per Pull Request (Schritt 10).

**Einschränkung:** Im Browser-Editor gibt es kein Live Server und kein Terminal. Die Vorschau läuft über GitHub Pages (Schritt 7).

## Schritt 3: Aufbau von index.html verstehen ✅

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

**Besonderheit:** `&lt;` und `&gt;` sind Ersatzzeichen für `<` und `>`, damit der Browser sie als Text anzeigt und nicht als Tag.

## Schritt 4: Erste Änderung und Commit und Push ✅

**Mini-Übung:**

- [x] In `index.html` den Text der Überschrift ändern (`Hallo MQ Welt!`).
- [ ] Nach dem ersten Absatz einen neuen einfügen: `<p>Ich lerne gerade HTML.</p>`
- [ ] In der Liste einen vierten Punkt ergänzen: `<li>Links mit <code>&lt;a&gt;</code></li>`
- [ ] Denkaufgabe: Was passiert, wenn bei einem `<li>` das `</li>` fehlt? Fehleranzeige unten (Zahlen neben dem Warndreieck) beobachten.

**Änderungen speichern = Commit und Push:**

1. Links auf das Symbol **Quellcodeverwaltung** (Verzweigungs-Symbol) tippen. Geänderte Dateien stehen unter „Änderungen“, markiert mit **M**.
2. In das Feld **„Nachricht“** eine kurze Notiz tippen, z. B. `Überschrift geändert`. Ohne Nachricht erscheint „Sie müssen vor dem Committen eine Commitnachricht angeben“.
3. Auf den blauen Button **„Commit und Push“** tippen. Rückfrage ggf. bestätigen.

**Woran ich erkenne, dass es geklappt hat:** Unter „Änderungen“ steht nichts mehr.

## Schritt 5: Repository öffentlich machen ✅

GitHub Pages (die Vorschau am iPad) gibt es bei kostenlosen Konten nur für **öffentliche** Repositories.

- [x] github.com → Repository **Annahof** → **Settings**.
- [x] **General** ganz nach unten → **Danger Zone** → **Change visibility** → **Public** → bestätigen.

**Woran ich erkenne, dass es geklappt hat:** Neben dem Repository-Namen steht nicht mehr „Private“.

**Wichtig:** Öffentlich heißt, jeder kann den Code lesen (nur ich kann ihn ändern). Keine Schülerdaten und nichts Privates ablegen.

**Alternative (privat bleiben):** Als Lehrer über https://education.github.com/teachers GitHub Pro gratis beantragen – dann geht Pages auch privat (Prüfung dauert ein paar Tage).

## Schritt 6: Branch `main` anlegen ✅

- [x] In vscode.dev unten links auf den Branch-Namen tippen.
- [x] **„+ Neuen Branch erstellen…“** → `main` eingeben → Enter.

**Woran ich erkenne, dass es geklappt hat:** Unten links steht `main`. Auf GitHub steht „2 Branches“.

## Schritt 7: GitHub Pages einschalten ✅

- [x] **Settings** → links **Pages**.
- [x] Source: **Deploy from a branch**.
- [x] Branch: **`main`**, Ordner: **`/ (root)`** → **Save**.

**Woran ich erkenne, dass es geklappt hat:** Oben steht „GitHub Pages source saved“ bzw. „Your site is live at …“. Nach 1–2 Minuten ist die Seite unter https://michaelquehenberger.github.io/Annahof/ erreichbar.

> ⚠️ **Nicht anklicken:** „Upgrade“, „Start free for 30 days“, „GitHub Enterprise“, „Configure“ bei Jekyll/Static HTML – unnötig bzw. kostenpflichtig. Steht bei Source plötzlich „GitHub Actions“: zurück auf **Deploy from a branch**.

## Schritt 8: Übung 1a – Liste mit Hobbys ✅

Datei: `uebungen/01-erste-seite/index.html` – im Explorer: `uebungen` → `01-erste-seite` → `index.html`. (Beide Dateien heißen `index.html`; welche offen ist, zeigt die Pfadzeile über dem Code.)

- [x] Unter den Kommentar eine Überschrift schreiben: `<h2>Meine Hobbys</h2>`
- [x] Darunter die Liste: `<ul>` als Rahmen, jedes Hobby in einem `<li>`
- [x] Ein Hobby mit `<strong>` fett machen
- [x] Commit und Push, Webseite neu laden, über „ersten Übung“ ansehen

```html
<h2>Meine Hobbys</h2>
<ul>
  <li><strong>Sport</strong></li>
  <li>Kochen</li>
  <li>Natur</li>
</ul>
```

**Feedback:** Struktur korrekt, `<strong>` richtig innerhalb von `<li>` verschachtelt. Kleinigkeiten: laut Duden „Hobby**s**“; Einrückung mit Rechtsklick → **Dokument formatieren** korrigieren.

**Ausprobieren:** `<ul>` gegen `<ol>` tauschen → nummerierte Liste.

## Schritt 9: Default branch auf `main` stellen ✅

**Warum:** Solange der Default noch der `claude/…`-Zweig ist, landen Änderungen, die ich direkt auf github.com mache, dort – und nicht auf `main` und meiner Webseite.

- [x] github.com → Repository **Annahof** → **Settings** (Zahnrad oben).
- [x] Links ist **General** schon ausgewählt. Abschnitt **Default branch** suchen (weit oben).
- [x] Rechts daneben auf das **Pfeil-Symbol ⇄** („Switch to another branch“) tippen.
- [x] Im Menü **`main`** auswählen → **Update**.
- [x] Warnhinweis („I understand, update the default branch“) bestätigen.

**Woran ich erkenne, dass es geklappt hat:** Unter „Default branch“ steht `main`. Auf der Code-Seite des Repos ist oben links `main` ausgewählt.

## Schritt 10: Claudes Änderungen per Pull Request übernehmen ✅

**Warum:** Claude legt Dateien (wie dieses Protokoll) auf seinem eigenen Zweig `claude/html-basics-vscodium-zio2y2` ab. Erst nach dem Übernehmen („Merge“) sind sie auf `main` – und damit in meinem Editor und auf meiner Webseite.

**Pull Request anlegen** (entfällt, wenn Claude ihn schon angelegt hat → weiter bei „Übernehmen“):

- [x] github.com → Repository **Annahof** → Reiter **Pull requests** → grüner Button **New pull request**.
- [x] Oben zwei Auswahlfelder einstellen: **base: `main`** ← **compare: `claude/html-basics-vscodium-zio2y2`**.
- [x] Darunter erscheinen die Änderungen (grün = neu, rot = entfernt). Kurz durchsehen.
- [x] **Create pull request** → Titel lassen oder z. B. „Lernprotokoll übernehmen“ → nochmals **Create pull request**.

**Übernehmen:**

- [x] Im Pull Request nach unten scrollen → grüner Button **Merge pull request** → **Confirm merge**.
- [x] Danach erscheint „Pull request successfully merged and closed“. Den Button „Delete branch“ brauche ich nicht zu tippen.

**Im Editor aktualisieren:**

- [x] vscode.dev neu laden (oder unten links neben `main` auf das Kreis-Pfeil-Symbol 🔄 tippen).

**Woran ich erkenne, dass es geklappt hat:** Im Explorer erscheint `anleitung.md`. Auf github.com ist sie in `main` sichtbar und wird dort schön formatiert angezeigt. In vscode.dev: Rechtsklick auf `anleitung.md` → **Vorschau öffnen**.

**Merke:** Immer wenn Claude etwas für mich ändert, kommt es auf diesem Weg zu mir: Pull Request → Merge → Editor aktualisieren. Ausführlich mit allen Varianten: **Täglicher Arbeitsablauf → Änderungen von Claude übernehmen**.

## Schritt 11: Übung 1b – Absatz und Link ⏳

Datei: `uebungen/01-erste-seite/index.html`

- [ ] Direkt unter `<h1>` einen Absatz über mich schreiben: `<p>Ich heiße … und …</p>`
- [ ] Einen Link zu meiner Lieblingsseite einfügen:
  ```html
  <p>Meine Lieblingsseite: <a href="https://www.orf.at">ORF</a></p>
  ```
  In `href="…"` steht die Adresse, zwischen `<a …>` und `</a>` der anklickbare Text.
- [ ] Commit und Push, Webseite neu laden, Link antippen.

**Woran ich erkenne, dass es geklappt hat:** Der Link ist blau unterstrichen und öffnet die Seite.

## Schritt 12: Bilder ⬜

Neue Übung `uebungen/02-bilder/` anlegen (siehe „Neue Übung anlegen“ oben) und auf der Startseite verlinken.

- [ ] Ein Bild in den Ordner `uebungen/02-bilder/bilder/` hochladen.
- [ ] Einbinden mit `<img src="bilder/foto.jpg" alt="Beschreibung">` (`alt` = Text für Screenreader bzw. wenn das Bild fehlt).

## Schritt 13: Tabellen ⬜

Neue Übung `uebungen/03-tabellen/`.

- [ ] `<table>`, `<tr>` (Zeile), `<th>` (Kopfzelle), `<td>` (Zelle)

## Schritt 14: Seitenaufbau ⬜

Neue Übung `uebungen/04-seitenaufbau/`.

- [ ] `<header>`, `<nav>`, `<main>`, `<footer>`

## Schritt 15: CSS ⬜

- [ ] Ordner `css/` im Hauptordner anlegen, darin `style.css`.
- [ ] Im `<head>` einbinden – Startseite: `<link rel="stylesheet" href="css/style.css">`, Übungsseiten: `<link rel="stylesheet" href="../../css/style.css">`
- [ ] Farben, Schrift, Layout gestalten.

---

# Täglicher Arbeitsablauf

### Am iPad – vscode.dev
1. Editor-Link öffnen.
2. **Unten links prüfen: steht `main`?** Wenn nicht → antippen und `main` wählen.
3. Datei im **Explorer** öffnen und bearbeiten.
4. Quellcodeverwaltung → Nachricht → **Commit und Push**.
5. Ca. 1 Minute warten → Tab mit meiner Webseite **neu laden** (ggf. zweimal).

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

### Änderungen von Claude übernehmen (Pull Request)

Claude speichert seine Änderungen nie direkt auf `main`, sondern auf seinem eigenen Zweig `claude/html-basics-vscodium-zio2y2`. Erst wenn ich sie per **Pull Request** übernehme („mergen“), sind sie auf `main` – in meinem Editor und auf meiner Webseite. So behalte ich die Kontrolle: Ich sehe vorher, was sich ändert.

**Woran ich erkenne, dass etwas wartet:** Claude sagt es mir im Chat – oder auf github.com erscheint ein gelbes Feld „claude/… had recent pushes“.

**Variante A – gelbes Feld ist da (schneller):**
1. github.com → **Annahof** → im gelben Feld **Compare & pull request**.
2. Prüfen: **base: `main`** ← **compare: `claude/html-basics-vscodium-zio2y2`**.
3. **Create pull request**.
4. Weiter bei „Übernehmen“.

**Variante B – kein gelbes Feld** (es verschwindet nach ca. einer Stunde):
1. github.com → **Annahof** → Reiter **Pull requests** → **New pull request**.
2. Einstellen: **base: `main`** ← **compare: `claude/html-basics-vscodium-zio2y2`**.
3. **Create pull request** → nochmals **Create pull request**.
4. Weiter bei „Übernehmen“.

**Variante C – Claude hat den Pull Request schon angelegt:**
1. github.com → **Annahof** → Reiter **Pull requests** → den offenen Pull Request antippen.
2. Weiter bei „Übernehmen“.

**Übernehmen:**
1. Optional: Reiter **Files changed** → ansehen, was sich ändert (grün = neu, rot = entfernt).
2. Unten **„No conflicts with base branch“**? → **Merge pull request** → **Confirm merge**.
3. Oben steht lila **„Merged“** → fertig. „Delete branch“ nicht nötig.
4. **vscode.dev neu laden** (oder 🔄 unten links neben `main`).

> ⚠️ **Steht dort „This branch has conflicts“?** Dann haben Claude und ich dieselbe Stelle geändert. Nicht selbst lösen – Claude Bescheid geben, Claude führt die Änderungen zusammen.

> 💡 **Tipp:** Bevor ich Claude um eine Änderung bitte, meine eigenen Änderungen committen. Dann gibt es kaum Konflikte.

### Git-Wörterbuch

| Begriff | Bedeutung |
|---|---|
| **Repository (Repo)** | Projektordner auf GitHub mit allen Dateien und ihrer Geschichte |
| **Commit** | Ein gespeicherter Zwischenstand mit Nachricht („Hobbyliste ergänzt“) |
| **Push** | Commits vom Editor zu GitHub hochladen |
| **Synchronisieren / Pull** | Neueste Änderungen von GitHub in den Editor holen |
| **Branch (Zweig)** | Eigener Arbeitsstand; mein Hauptzweig ist `main` |
| **Pull Request (PR)** | Anfrage: „Übernimm die Änderungen von Zweig X nach `main`“ |
| **Merge** | Das Übernehmen selbst – die Änderungen landen auf `main` |
| **Konflikt** | Beide Zweige haben dieselbe Stelle unterschiedlich geändert |

### Nützliche Tricks
- `!` + **Tab** in leerer HTML-Datei → komplettes Grundgerüst
- `ul>li*3` + **Tab** → Liste mit 3 Punkten (nur mit echter Tastatur)
- Rechtsklick im Code → **Dokument formatieren** → Einrückung automatisch
- Statusleiste unten: ⓧ 0 ⚠ 0 = keine Fehler
- Externe Tastatur am iPad erleichtert `<`, `>`, `/`, `"` enorm

---

# HTML-Spickzettel

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
| `<ul>` | Aufzählung mit Punkten | siehe Schritt 8 |
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
- Dateinamen klein, ohne Leerzeichen und Umlaute: `ueber-mich.html` (alle Regeln: siehe „Grundregeln“ oben)
- `&lt;` und `&gt;` zeigen `<` und `>` als Text an

---

## Notizen

*(Platz für eigene Notizen, Fragen, Aha-Momente)*

-
