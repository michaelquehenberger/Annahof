# Anleitung – HTML & CSS Schritt für Schritt

Meine persönliche Dokumentation: Was ich eingerichtet habe, wie ich arbeite und was als Nächstes kommt.

**Wichtige Links**

- Meine Webseite: https://michaelquehenberger.github.io/Annahof/
- Editor (iPad/Browser): https://vscode.dev/github/michaelquehenberger/Annahof/tree/main?vscode-lang=de-de
- Repository: https://github.com/michaelquehenberger/Annahof

---

## Teil 1: Einrichtung (erledigt ✅)

### 1.1 GitHub-Repository anlegen
- [x] GitHub-Konto angelegt
- [x] Repository `Annahof` erstellt
- [x] Startstruktur: `index.html`, `uebungen/`, `bilder/`, `README.md`

### 1.2 Branch `main` anlegen
Ein **Branch** ist ein Arbeitsstand. `main` ist der Hauptbranch – auf ihm arbeite ich.

- [x] In vscode.dev unten links auf den Branch-Namen tippen → **Neuen Branch erstellen…** → `main`
- [ ] Auf GitHub: **Settings → General → Default branch** → `main` → *Update*

### 1.3 Repository öffentlich machen
GitHub Pages ist mit einem kostenlosen Konto nur bei öffentlichen Repos möglich.

- [x] **Settings → General** → ganz unten *Danger Zone* → **Change visibility → Public**
- ⚠️ Keine privaten Daten (Adresse, Telefonnummer, Passwörter) in den Code schreiben – jeder kann ihn lesen.

### 1.4 GitHub Pages einschalten
- [x] **Settings → Pages**
- [x] Source: **Deploy from a branch**
- [x] Branch: **`main`**, Ordner: **`/ (root)`** → *Save*
- [x] Nach 1–2 Minuten ist die Seite online.

> ⚠️ **Nicht anklicken:** „Upgrade“, „Start free for 30 days“, „GitHub Enterprise“, „Configure“ bei Jekyll/Static HTML – alles unnötig bzw. kostenpflichtig.

---

## Teil 2: So arbeite ich (jedes Mal)

### Am iPad – vscode.dev
1. Editor-Link öffnen (oder auf GitHub im Repo die Taste **`.`** drücken).
2. **Unten links prüfen: Steht dort `main`?** Wenn nicht → antippen und `main` wählen.
3. Datei im **Explorer** (links, oberstes Symbol) öffnen und bearbeiten.
4. **Speichern = Commit & Push:**
   - Links auf das **Verzweigungs-Symbol** (Quellcodeverwaltung) tippen
   - Kurze Nachricht eingeben, z. B. `Hobbyliste ergänzt`
   - **Commit und Push** tippen
5. Ca. 1 Minute warten → Tab mit meiner Webseite **neu laden** → Ergebnis ansehen.

> ⚠️ Änderungen in vscode.dev sind nur im Browser, bis ich committe. Am Ende jeder Arbeitsphase **immer committen**!

### Am PC – VSCodium
1. **Datei → Ordner öffnen** → Projektordner wählen.
2. **Zuerst synchronisieren** (holt die Änderungen vom iPad).
3. Bearbeiten, Vorschau mit **Live Server**: Rechtsklick auf die HTML-Datei → *Open with Live Server*.
4. Quellcodeverwaltung → Nachricht → **Commit** → **Änderungen synchronisieren**.

### Unterschiede iPad ↔ PC

| | VSCodium (PC) | vscode.dev (iPad) |
|---|---|---|
| Hochladen | Commit, dann Synchronisieren | Commit und Push (ein Schritt) |
| Vorschau | Live Server | Meine Webseite neu laden |
| Terminal | ✅ | ❌ |

### Nützliche Tricks
- `!` + **Tab** in leerer HTML-Datei → komplettes Grundgerüst
- `ul>li*3` + **Tab** → Liste mit 3 Punkten (nur mit echter Tastatur)
- Rechtsklick im Code → **Dokument formatieren** → richtet die Einrückung aus
- Unten in der Statusleiste: ⓧ 0 ⚠ 0 = keine Fehler

---

## Teil 3: HTML-Grundlagen (Spickzettel)

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
| `<ul>` | Aufzählung mit Punkten | siehe unten |
| `<ol>` | nummerierte Liste | siehe unten |
| `<li>` | ein Listenpunkt | `<li>Kochen</li>` |
| `<strong>` | fett / wichtig | `<strong>Sport</strong>` |
| `<a href="…">` | Link | `<a href="https://www.orf.at">ORF</a>` |

### Liste
```html
<h2>Meine Hobbys</h2>
<ul>
  <li><strong>Sport</strong></li>
  <li>Kochen</li>
  <li>Natur</li>
</ul>
```

### Links
- **Externe Seite:** volle Adresse mit `https://` → `<a href="https://www.orf.at">ORF</a>`
- **Eigene Seite:** relativer Pfad → `<a href="uebungen/01-erste-seite/index.html">Übung 1</a>`
- `../` heißt „einen Ordner nach oben“ → `<a href="../../index.html">Zurück</a>`

### Regeln
- Jedes geöffnete Tag wird geschlossen: `<p>` … `</p>` (Ausnahmen: `<br>`, `<img>`, `<meta>`)
- Tags richtig verschachteln: `<li><strong>…</strong></li>` ✅ – nicht `<li><strong>…</li></strong>` ❌
- Dateinamen klein, ohne Leerzeichen und Umlaute: `ueber-mich.html`

---

## Teil 4: Fortschritt

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
- [ ] Danach: **CSS** – eigene Datei `style.css`, eingebunden mit `<link rel="stylesheet" href="style.css">`

---

## Notizen

*(Platz für eigene Notizen, Fragen, Aha-Momente)*

-
