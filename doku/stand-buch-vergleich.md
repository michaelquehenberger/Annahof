# Stand im Vergleich zum Buch

**Buch:** Peter Müller, *Einstieg in HTML und CSS*, Rheinwerk Verlag, 3. Auflage 2024 (24 Kapitel, ca. 540 Seiten)
**Stand vom:** 14.10.2026

## Kurz gesagt

Wir sind **mitten in Kapitel 6 (Bilder)**, das ist etwa Seite 120 von 540, also gut ein Fünftel des Buchs.

## Kapitel für Kapitel

Legende: ✅ erledigt · 🟡 teilweise · ⏳ läuft gerade · ⬜ noch offen

| Kap. | Thema | Stand | Was fehlt noch |
|---|---|---|---|
| 1 | Wissenswertes über Webseiten (Browser, Editoren) | ✅ | – (unser Editor: VSCodium bzw. vscode.dev) |
| 2 | HTML kennenlernen: die erste Webseite | 🟡 | `<meta name="description">` (2.7.4), `<header>` mit Überschrift und Slogan (2.9), Entwicklerwerkzeuge im Browser (2.10) |
| 3 | CSS kennenlernen: die erste Webseite gestalten | ⬜ | **übersprungen**: `style.css` anlegen, mit `<link>` einbinden, Farben für `body` und `header`, `padding` |
| 4 | Überschriften, Absätze, Hervorhebungen, Listen | 🟡 | `<em>`, `<ol>`, verschachtelte Listen, Block- und Inline-Elemente |
| 5 | Hyperlinks | 🟡 | Links (auch relative) und `target="_blank"` sind erledigt. Offen: Navigation als Liste, Link „Nach oben“, `mailto:`, Links auf PDFs |
| 6 | Bilder, Audio und Video | ⏳ | `<img>` mit `alt` und `width` ✅. Offen: `<figure>`/`<figcaption>`, `loading="lazy"`, `max-width: 100%`, Bilder für hochauflösende Bildschirme, `<audio>`, `<video>` |
| 7 | Semantische Elemente (`header`, `nav`, `main`, `footer`, `section`, `article`, `aside`) | ⬜ | entspricht unserem Schritt 14 „Seitenaufbau“ |
| 8 | Weitere Textelemente (`blockquote`, `address`, `time`, `details` …) | ⬜ | |
| 9 | Formulare | ⬜ | |
| 10 | Tabellen | ⬜ | entspricht unserem Schritt 13 |
| 11 | Von der Webseite zur Website | ⬜ | |
| 12–18 | CSS-Grundlagen (Box-Modell, Farben, Selektoren, Schriften, Kaskade) | ⬜ | entspricht unserem Schritt 15 |
| 19–24 | CSS-Layout (Flexbox, Grid, Media Queries, responsive Navigation) | ⬜ | |

## Wo wir vom Buch abweichen

1. **CSS kommt bei uns später.** Das Buch führt CSS schon in Kapitel 3 ein. Teil II heißt „HTML (mit einer Prise CSS)“: Jede neue HTML-Übung bekommt dort gleich etwas Gestaltung dazu. Bei uns steht CSS erst bei Schritt 15.
2. **Einzelne Übungsseiten statt einer durchgehenden Website.** Im Buch wächst ab Kapitel 2 eine Website mit Header, Navigation und Footer, die in Kapitel 11 Unterseiten bekommt. Wir legen pro Übung einen eigenen Ordner an (`uebungen/01-…`, `02-…`). Die Startseite `index.html` könnte schrittweise zu so einer Website werden.
3. **Reihenfolge der nächsten Schritte.** Wir haben Tabellen (Kap. 10) vor dem Seitenaufbau (Kap. 7) geplant. Das Buch macht zuerst Seitenaufbau und Semantik.

## Begriffe, die man leicht verwechselt

- **`<head>`** ist der unsichtbare Kopf des Dokuments: `charset`, `viewport`, `<title>`, später der `<link>` zum Stylesheet. Den haben wir in jeder Seite ✅.
- **`<header>`** ist der **sichtbare** Kopfbereich *im* `<body>`, z. B. Website-Name und Slogan. Den haben wir noch nicht.

```html
<body>
  <header>
    <h1>Annahof</h1>
    <p>Mein Slogan</p>
  </header>
  ...
</body>
```

- **Entwicklerwerkzeuge im Browser:** Damit sieht man das HTML (und später das CSS) einer Seite direkt im Browser und kann es ausprobieren.
  - Am PC (Chrome, Edge, Firefox): **F12** oder Rechtsklick → **Untersuchen**.
  - Am iPad gibt es in Safari keine Entwicklerwerkzeuge. Dafür braucht man den PC (oder einen Mac).

## Nächste Schritte (Vorschlag)

1. **Übung 2 im Sinne von Kapitel 6 abschließen:** Bild in `<figure>` setzen, `<figcaption>` statt des `<p>` darunter, `loading="lazy"` ergänzen.
2. **Kapitel 2 nachholen:** `<meta name="description">` und einen `<header>` auf der Startseite einbauen, Entwicklerwerkzeuge am PC einmal ausprobieren.
3. **Kapitel 3 einschieben:** erste `style.css`, dazu `img { max-width: 100%; }`.
4. **Dann Kapitel 7** (Seitenaufbau) und danach Kapitel 10 (Tabellen).
