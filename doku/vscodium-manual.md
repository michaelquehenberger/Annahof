# Webseiten bauen mit VSCodium – Schritt-für-Schritt-Manual

Stand: 13. Okt. 2026 · @Michael

## Einleitung

Nach diesem Manual baust du deine erste eigene Website und siehst sie live im Browser. Du arbeitest mit **VSCodium**, einem kostenlosen Code-Editor. Er entspricht Microsofts VS Code, nur ohne Telemetrie. Jede Anleitung für VS Code gilt also auch hier.

**Das brauchst du:**

- einen Computer mit VSCodium (installiert oder als Portable-Version)

- einen Browser (Firefox, Chrome oder Edge)

- einen Speicherort für deinen Projektordner (Netzlaufwerk, OneDrive oder USB-Stick)

**Hinweise für Lehrkräfte**

- Ohne Admin-Rechte an den Schulrechnern läuft die Portable-Version (ZIP) von VSCodium vom Netzlaufwerk oder USB-Stick.

- Mit der Schul-IT klären: Ist der Extension-Marktplatz (open-vsx.org) im Schulnetz erreichbar? Sind GitHub bzw. Netlify freigeschaltet?

- Datenschutz: In Österreich willigen Jugendliche erst ab 14 selbst ein. Auf veröffentlichten Seiten stehen keine echten Namen, Fotos oder Adressen von Schülerinnen und Schülern, außer mit schriftlicher Einwilligung.

## Vorab: Welcher Editor? VSCodium, VS Code oder Browser

**Kurz:** Für HTML, CSS und Git ist es praktisch egal. VSCodium *ist* VS Code – gleicher Code, gleiche Oberfläche, gleiche Tastenkürzel, nur ohne Microsoft-Branding und Telemetrie. Für den Unterricht ist VSCodium trotzdem die beste Wahl.

**VSCodium und VS Code im Vergleich**

| | VS Code | VSCodium |
|---|---|---|
| Datenübertragung an Microsoft | ja (abschaltbar) | nein |
| Extensions kommen aus | Microsoft Marketplace | Open VSX (open-vsx.org) |
| Live Server, German Language Pack | ✅ | ✅ |
| Einige Microsoft-Extensions (z. B. Live Share) | ✅ | ❌ |
| Einstellungen geräteübergreifend synchronisieren | ✅ (mit Konto) | ❌ |
| Im Browser (vscode.dev, github.dev) | das *ist* VS Code | – |

**Speichern, Ansehen, Veröffentlichen – was hängt vom Editor ab?**

- **Speichern** geht grundsätzlich überall:
  - *VSCodium* speichert in einen Ordner auf dem Rechner, dem Netzlaufwerk oder einem USB-Stick.
  - *vscode.dev im Browser* speichert entweder mit GitHub-Konto direkt ins Repository oder ohne Konto über *Open Folder* in einen lokalen Ordner – Letzteres **nur in Chrome und Edge**, nicht in Firefox oder Safari.
- **Ansehen** geht auch ohne Live Server: Doppelklick auf `index.html` öffnet die Seite im Browser. Live Server ist nur bequemer, weil er nach dem Speichern automatisch neu lädt.
- **Veröffentlichen** kann kein Editor von sich aus. Das läuft immer über einen eigenen Weg: GitHub, Schul-Webspace oder Netlify (Kapitel 5 und 6).

**Warum VSCodium für die Klasse?**

| | VSCodium | vscode.dev (Browser) |
|---|---|---|
| Konto nötig | nein | GitHub-Konto (oder Chrome/Edge mit lokalem Ordner) |
| Funktioniert offline | ✅ | ❌ |
| Live Server | ✅ | ❌ |
| Datenschutz (Schüler unter 14) | ✅ alles bleibt lokal | ⚠️ Konto bei einem US-Dienst |
| Abgabe über Netzlaufwerk | ✅ einfach | umständlich |

**Empfehlung**

- **Schülerinnen und Schüler:** VSCodium – lokal, ohne Konten, datenschutzfreundlich.
- **Lehrkraft am Laptop:** ebenfalls VSCodium, damit Anleitungen und Screenshots 1:1 zu dem passen, was die Klasse sieht. Nicht zusätzlich VS Code installieren – zwei Editoren mit getrennten Einstellungen und Extensions verwirren nur.
- **Lehrkraft am iPad:** vscode.dev bzw. github.dev (eine andere Möglichkeit gibt es dort nicht). Commit speichert direkt auf GitHub; kein Live Server, Vorschau über GitHub Pages.

## Kapitel 1: VSCodium kennenlernen

Die VSCodium-Oberfläche besteht aus vier Bereichen. Beim ersten Start siehst du in der Mitte die Willkommensseite mit **Start** (New File, Open File, Open Folder) und **Walkthroughs**.

| Bereich                 | Wo?                          | Wofür?                                                                      |
|-------------------------|------------------------------|-----------------------------------------------------------------------------|
| Aktivitätsleiste        | ganz links, senkrechte Icons | oben Explorer (Dateien), dann Suche, Git, Debuggen, Extensions (4 Kästchen) |
| Seitenleiste            | rechts neben der Icon-Leiste | zeigt z. B. die Dateien deines Projektordners                               |
| Editor                  | Mitte                        | hier bearbeitest du Dateien, jede geöffnete Datei ist ein Tab               |
| Terminal / Statusleiste | unten                        | Terminal über Strg + Ö, in der Statusleiste später der Button „Go Live“     |

**Merke:** VSCodium arbeitet immer mit einem **Projektordner**, nicht mit einzelnen Dateien.

**Optional: VSCodium auf Deutsch**

1.  Links auf das Extensions-Symbol klicken.

2.  Nach **German Language Pack** suchen und auf **Install** klicken.

3.  VSCodium neu starten, wenn es danach fragt.

Dieses Manual nennt die Menüpunkte auf Englisch, so wie sie standardmäßig erscheinen.

## Kapitel 2: Projektordner anlegen und öffnen

Alle Dateien deiner Website liegen in einem eigenen Ordner, den du in VSCodium öffnest.

1.  Auf der Willkommensseite auf **Open Folder…** klicken (alternativ: Menü **File → Open Folder…**).

2.  Zum Speicherort gehen, z. B. **Dokumente** oder dein Netzlaufwerk.

3.  Auf **Neuer Ordner** klicken und ihn meine-erste-website nennen.

4.  Den Ordner markieren und auf **Ordner auswählen** klicken.

5.  Erscheint die Frage *„Do you trust the authors of the files in this folder?“*, auf **Yes, I trust the authors** klicken. Es ist dein eigener Ordner.

**Ergebnis:** Links im Explorer steht jetzt der (noch leere) Ordner MEINE-ERSTE-WEBSITE.

**Tipp:** Ordner- und Dateinamen am besten klein schreiben, ohne Leerzeichen und ohne Umlaute (also ueber-mich.html statt Über mich.html). Das vermeidet später Probleme beim Veröffentlichen.

## Kapitel 3: Die erste Seite – index.html

Die Startseite jeder Website heißt index.html. Diesen Namen sucht der Browser bzw. Server automatisch.

1.  Im Explorer mit der Maus über den Ordnernamen fahren. Es erscheinen kleine Symbole.

2.  Auf **New File…** klicken (Blatt mit Plus).

3.  Als Namen genau index.html eingeben und **Enter** drücken.

4.  In die leere Datei ein **Ausrufezeichen !** tippen und **Enter** drücken. VSCodium erzeugt das HTML-Grundgerüst automatisch.

5.  Die Zeile `<body>` suchen und zwischen `<body>` und `</body>` schreiben:

```html
<h1>Hallo Welt!</h1>
<p>Meine erste Website.</p>
```

6.  Mit **Strg + S** speichern.

**Gespeichert oder nicht?** Ein **weißer Punkt** im Tab neben index.html heißt: noch nicht gespeichert. Nach Strg + S wird daraus ein ✕.

**Zum Verstehen:** `<h1>` ist die Hauptüberschrift, `<p>` ein Absatz. Fast jedes HTML-Element hat ein öffnendes Tag `<p>` und ein schließendes Tag `</p>`.

**Tipp: Seitentitel ändern.** Im Grundgerüst steht `<title>Document</title>`. Dieser Text erscheint im Browser-Tab. Ersetze Document durch einen eigenen Titel, z. B. `<title>Meine erste Website</title>`.

## Kapitel 4: Live Server – die Seite im Browser ansehen

Mit der Extension **Live Server** öffnet sich deine Seite im Browser und lädt bei jedem Speichern automatisch neu.

1.  Links auf das **Extensions-Symbol** klicken (4 Kästchen).

2.  Oben ins Suchfeld live server eingeben.

3.  **Live Server** von **ritwickdey** anklicken (lila Symbol, über 3 Millionen Downloads). Achtung: Es gibt viele ähnlich benannte Extensions.

4.  Auf den blauen Button **Install** klicken. Fragt VSCodium nach Vertrauen in den Herausgeber, mit **Trust Publisher & Install** bestätigen.

5.  Zurück zum Tab index.html wechseln. Die Datei muss gespeichert sein (kein weißer Punkt).

6.  Unten rechts in der Statusleiste auf **Go Live** klicken.

**Ergebnis:** Der Browser öffnet sich mit einer Adresse wie http://127.0.0.1:5500 und zeigt „Hallo Welt!“.

**Ausprobieren:** Ändere den Text in `<h1>`, speichere mit Strg + S und schau in den Browser. Die Seite aktualisiert sich von selbst.

**Wichtig:** Diese Adresse funktioniert nur auf deinem eigenen Rechner. Damit andere deine Seite sehen, musst du sie veröffentlichen (Kapitel 5). Zum Beenden in der Statusleiste auf **Port: 5500** klicken.

**Achtung bei Links auf Unterseiten:** Ein Link wie `<a href="uebungen/01-erste-seite/">` zeigt auf einen **Ordner**. Ein Webserver (GitHub Pages, Live Server) sucht darin automatisch nach `index.html` und zeigt sie an. Öffnest du die Seite aber direkt als Datei (Adresse beginnt mit `file:///`), gibt es keinen Webserver: Der Browser zeigt nur eine Dateiliste oder gar nichts. Darum online „geht's“, lokal nicht.

Lösung: Im Link immer die **Datei** angeben, nicht nur den Ordner:

```html
<a href="uebungen/01-erste-seite/index.html">Übung 1</a>
```

So funktioniert der Link überall: lokal, mit Live Server und auf GitHub Pages.

## Kapitel 5: Website veröffentlichen mit GitHub Pages

Mit GitHub Pages ist deine Website kostenlos unter einer Adresse wie https://NAME.github.io/webseiten-3a/ für alle erreichbar. Alles läuft im Browser, du musst nichts installieren. Dieses Kapitel führt die **Lehrkraft** durch: Die Schüler geben ihren Ordner ab, und du lädst ihn hoch.

**Einmalig: Konto und Repository anlegen**

1.  Auf [github.com](https://github.com) ein kostenloses Konto erstellen (Lehrer-Konto, z. B. mit der Schul-Mailadresse). Der Benutzername steht später in der Web-Adresse.

2.  Rechts oben auf **+** und dann auf **New repository** klicken.

3.  **Repository name:** z. B. webseiten-3a (eines pro Klasse, klein, ohne Leerzeichen).

4.  **Public** auswählen. GitHub Pages ist im Gratis-Konto nur für öffentliche Repositories verfügbar.

5.  Häkchen bei **Add a README file** setzen und auf **Create repository** klicken.

**Repository versehentlich als Private angelegt?** Dann im Repository auf **Settings** klicken (Reiter General), ganz nach unten zur **Danger Zone** scrollen und dort **Change visibility → Change to public** wählen. Die Abfrage bestätigen. Ohne diesen Schritt fehlt im Gratis-Konto die Option Pages.

**Mit GitHub Education (Lehrkräfte):** Ist auf dem Konto GitHub Pro aktiv, funktioniert Pages auch mit **privaten** Repositories. Eine Education-Lizenz allein reicht dafür nicht immer. Prüfen lässt sich das unter **Settings → Pages**: Steht dort *„Upgrade or make this repository public to enable Pages“*, ist Pro nicht aktiv. Dann das Repository auf Public umstellen (siehe oben) und **nicht** auf *Upgrade* klicken, denn das ist kostenpflichtig. Wichtig: Die veröffentlichte Website ist in jedem Fall für alle sichtbar, privat bleibt nur die Repository-Ansicht auf GitHub.

**Dateien hochladen**

1.  Im Repository auf **Add file → Upload files** klicken.

2.  Den **Inhalt** des Projektordners (also index.html und alles andere) ins Browserfenster ziehen. Bei einer Klasse zieht man stattdessen die Schüler-Ordner hinein (siehe unten).

3.  Unten auf **Commit changes** klicken.

**GitHub Pages einschalten (einmalig)**

1.  Im Repository oben auf **Settings** klicken, links auf **Pages**.

2.  Bei **Source** die Option **Deploy from a branch** wählen.

3.  Bei **Branch** main und / (root) wählen und auf **Save** klicken.

4.  1–2 Minuten warten und die Seite neu laden. Oben erscheint *„Your site is live at …“* mit der Adresse.

**Hinweise aus der Praxis**

- Das Feld **Branch** erscheint erst, wenn das Source-Dropdown geschlossen ist (Esc drücken). Dort steht zunächst **None**. Erst nach der Auswahl von main und einem Klick auf **Save** ist Pages eingeschaltet.

- Den Fortschritt zeigt der Reiter **Actions**: Der Eintrag *„pages build and deployment“* läuft etwa eine Minute. Wird er grün, ist die Seite online.

- Bis dahin zeigt die Adresse *„404 – There isn't a GitHub Pages site here“*. Das ist normal, einfach kurz warten und neu laden.

**Ordnerstruktur für eine ganze Klasse**

webseiten-3a/  
index.html ← Übersichtsseite mit Links zu allen Projekten  
projekt-01/  
index.html  
projekt-02/  
index.html

Die Seite von projekt-01 ist dann unter https://NAME.github.io/webseiten-3a/projekt-01/ erreichbar. Ordner mit Nummern oder Fantasienamen statt echter Namen benennen.

**Änderungen veröffentlichen:** Die geänderten Dateien erneut über **Upload files** hochladen. Gleichnamige Dateien werden ersetzt. Nach 1–2 Minuten ist die neue Version online. Wird eine Seite nicht aktualisiert, hilft **Strg + F5** im Browser.

**Achtung:** Öffentlich heißt, dass alle Dateien im Repository von jedem gelesen werden können. Deshalb keine Passwörter, privaten Daten, echten Namen oder Fotos ohne Einwilligung hochladen.

## Kapitel 6: Alternativen zu GitHub

Die Schüler brauchen auch bei GitHub Pages kein eigenes Konto, wenn die Lehrkraft hochlädt (Kapitel 5). Sollen sie selbst veröffentlichen oder soll es ganz ohne GitHub gehen, gibt es diese Wege:

| Weg                                          | Wer braucht ein Konto? | Vorteil                                                              | Haken                                                                                    |
|----------------------------------------------|------------------------|----------------------------------------------------------------------|------------------------------------------------------------------------------------------|
| Schul-Webspace (Upload z. B. mit FileZilla)  | niemand extern         | Daten bleiben bei der Schule, am besten für den Datenschutz          | nur wenn die Schule Webspace hat; Zugangsdaten über die Schul-IT                         |
| [Netlify Drop](https://app.netlify.com/drop) | ohne Konto möglich     | Ordner ins Browserfenster ziehen, nach Sekunden online               | ohne Konto nur vorübergehend online; dauerhaft nur mit Konto, Gratis-Kontingent begrenzt |
| [Neocities](https://neocities.org)           | jeder Schüler          | eigener Editor im Browser, für kleine selbstgebaute Seiten gedacht   | Konto pro Schüler (laut Nutzungsbedingungen ab 13), Seiten sind öffentlich               |
| Nicht veröffentlichen                        | niemand                | Präsentation in der Klasse über Live Server, Abgabe per Netzlaufwerk | nur im Klassenzimmer sichtbar                                                            |

**Empfehlung**

- Zum Einstieg arbeiten die Schüler lokal und präsentieren mit Live Server. Am Projektende veröffentlicht die Lehrkraft die Seiten gesammelt.

- Zuerst bei der Schul-IT nach eigenem Webspace fragen. Der ist datenschutzrechtlich die sauberste Lösung.

- Netlify Drop eignet sich für einen schnellen „Meine Seite ist im Internet!“-Moment im Unterricht, auch ohne Konten.

## Kapitel 7: Mehrere Projekte – mit und ohne GitHub

In VSCodium sind beliebig viele Projekte nebeneinander möglich, manche mit GitHub, manche ohne. Jeder Projektordner ist unabhängig von den anderen.

| Art des Projekts          | Was es ist                                              | Wofür                                                                       |
|---------------------------|---------------------------------------------------------|-----------------------------------------------------------------------------|
| Normaler Ordner           | nur Dateien, ohne Versionsverlauf                       | Schüler-Projekte, schnelle Übungen                                          |
| Lokales Git-Repository    | Ordner mit Versionsverlauf, nur auf dem eigenen Rechner | eigene Projekte mit Sicherheitsnetz (Änderungen zurückholen), ohne Internet |
| Git-Repository mit GitHub | Versionsverlauf plus Kopie auf GitHub                   | alles, was über GitHub Pages veröffentlicht wird                            |

**Begriffe:** *Git* ist das Programm für den Versionsverlauf, es läuft auf dem eigenen Rechner. *GitHub* ist ein Online-Dienst, auf den man Git-Repositories hochladen kann. Git funktioniert auch ganz ohne GitHub.

**Mehrere Projekte öffnen**

- **Neues Fenster:** *File → New Window*, dort *Open Folder…*. Jedes Projekt hat sein eigenes Fenster.

- **Schnell wechseln:** *File → Open Recent* oder **Strg + R** zeigt die zuletzt geöffneten Projekte.

- **Mehrere Ordner in einem Fenster:** *File → Add Folder to Workspace…* (Fortgeschrittene).

**Lokales Git-Repository ohne GitHub anlegen** (Git muss installiert sein)

1.  Projektordner in VSCodium öffnen.

2.  Links auf **Source Control** klicken (Symbol mit Verzweigung).

3.  Auf **Initialize Repository** klicken.

4.  Ab jetzt Änderungen mit kurzer Beschreibung und **Commit** speichern. Nichts wird hochgeladen.

Ein lokales Repository lässt sich später jederzeit mit GitHub verbinden (**Publish Branch**).

## Kapitel 8: Git einrichten und aus VSCodium veröffentlichen (Lehrkraft)

Mit Git veröffentlichst du Änderungen direkt aus VSCodium, ohne Upload im Browser. Die Einrichtung ist einmalig und dauert etwa 10 Minuten.

**1. Git für Windows installieren**

Installer von [git-scm.com](https://git-scm.com) laden oder per Befehl `winget install --id Git.Git -e --source winget` installieren. Im Installer:

| Fenster                                  | Auswahl                                                                  |
|------------------------------------------|--------------------------------------------------------------------------|
| Choosing the default editor              | Use VSCodium as Git's default editor                                     |
| Adjusting the name of the initial branch | Override the default branch name, Feld: main                             |
| Adjusting your PATH environment          | Git from the command line and also from 3rd-party software (Recommended) |
| Choosing the SSH executable              | Use bundled OpenSSH                                                      |
| Choosing HTTPS transport backend         | Use the native Windows Secure Channel library (wichtig in Schulnetzen)   |
| Line ending conversions                  | Checkout Windows-style, commit Unix-style                                |
| Terminal emulator                        | Use MinTTY                                                               |
| Default behavior of git pull             | Merge                                                                    |
| Credential helper                        | Git Credential Manager                                                   |
| Extra options                            | Voreinstellung lassen, dann Install                                      |

Danach **VSCodium neu starten**.

**2. Name und E-Mail für Git festlegen (einmalig)**

Im VSCodium-Terminal (Strg + Ö) eingeben:

```
git config --global user.name "Vorname Nachname"
git config --global user.email "ID+benutzername@users.noreply.github.com"
```

Die **noreply-Adresse** von GitHub schützt die echte Mailadresse, denn sie steht in jeder veröffentlichten Änderung. Die eigene Adresse findest du auf GitHub unter **Settings → Emails**.

**3. Repository in VSCodium holen (Clone)**

1.  In VSCodium **Strg + Shift + P** drücken, Git: Clone eintippen und Enter drücken.

2.  Die Repository-Adresse einfügen, z. B. https://github.com/BENUTZERNAME/vscodium-website-test.git, und Enter drücken.

3.  Einen Speicherort wählen, z. B. einen Ordner Dokumente\GitHub.

4.  Auf die Frage *„Would you like to open the cloned repository?“* mit **Open** antworten.

**Variante über „Clone from GitHub“:** Bietet VSCodium beim Clonen *Clone from GitHub* an, meldet man sich einmalig mit einem Code an. VSCodium zeigt ein Fenster *„Your Code: XXXX-XXXX“*. Dort auf **Copy & Continue to Browser** klicken. Im Browser prüfen, dass die Adresse mit https://github.com/login/device beginnt, den Code einfügen und **Authorize** bestätigen. Danach zurück in VSCodium, wo eine Liste der eigenen Repositories zur Auswahl erscheint.

**Auf die Frage *„Would you like to open the repository, or add it to the current workspace?“*** mit **Open** antworten. So ist das Repository ein eigenes Projekt, und Source Control zeigt nur dessen Änderungen.

**Achtung, zwei Ordner:** Nach dem Clonen gibt es den alten Übungsordner und die geclonte Kopie. Nur Änderungen in der **geclonten Kopie** lassen sich aus VSCodium veröffentlichen. Ab jetzt nur noch dort arbeiten. Den alten Ordner kann man als Sicherung behalten oder später löschen. Erkennbar ist die richtige Kopie daran, dass im Explorer auch README.md liegt und Source Control kein *Initialize Repository* anbietet.

**4. Änderungen veröffentlichen**

1.  Datei ändern und speichern (Strg + S).

2.  Links auf **Source Control** klicken (Symbol mit Verzweigung, zeigt die Anzahl geänderter Dateien).

3.  Oben eine kurze Beschreibung eintippen, z. B. Titel geändert.

4.  Auf **Commit** klicken, dann auf **Sync Changes**.

5.  Beim ersten Mal öffnet sich ein Browserfenster zur GitHub-Anmeldung. Anmelden und bestätigen.

Nach etwa einer Minute ist die neue Version online.

**Hat es geklappt?** Unten in Source Control zeigt der Bereich **Graph** alle Commits. Stehen beim obersten Eintrag die Markierung **main** und das **Wolken-Symbol** nebeneinander, ist die Änderung auf GitHub angekommen. Steht die Wolke weiter unten, fehlt noch **Sync Changes**.

**Seite zeigt noch die alte Version?** Der Browser merkt sich Seiten eine Weile (Cache). Mit **Strg + F5** lädt er die neueste Version. Unter **Actions** auf GitHub sieht man, ob *pages build and deployment* schon grün ist.

**Die Seite ansehen:** Veröffentlicht unter https://BENUTZERNAME.github.io/REPOSITORY/ (als Lesezeichen speichern), lokal während der Arbeit über **Go Live** in VSCodium.

## Kapitel 9: Ein neues Projekt starten

Jedes neue Projekt beginnt mit einem eigenen Ordner. Ob es auf GitHub kommt, entscheidest du am Anfang oder auch erst später.

**Ordnung halten:** Alle Projekte in einem gemeinsamen Ordner sammeln, z. B. Dokumente\GitHub für Projekte mit GitHub und Dokumente\Projekte für alles andere. Ordnernamen klein, ohne Leerzeichen und Umlaute, z. B. klasse-3a-2026.

**Weg A: Projekt mit GitHub (wird veröffentlicht)**

1.  Im Windows-Explorer einen neuen Ordner anlegen, z. B. Dokumente\GitHub\mein-neues-projekt.

2.  In VSCodium **File → Open Folder…** wählen und den Ordner öffnen.

3.  Erste Datei index.html anlegen, mit ! + Enter das Grundgerüst erzeugen, Inhalt schreiben und speichern.

4.  Links auf **Source Control** klicken und dann auf **Publish to GitHub**.

5.  Oben den Repository-Namen bestätigen und **Publish to GitHub public repository** wählen (Public ist für Pages im Gratis-Konto nötig).

6.  Fragt VSCodium, welche Dateien hochgeladen werden sollen, alle angehakt lassen und **OK** klicken.

7.  Auf GitHub im neuen Repository **Settings → Pages** öffnen, *Deploy from a branch* wählen, bei Branch main und / (root) wählen und auf **Save** klicken.

8.  Nach etwa einer Minute ist die Seite unter https://BENUTZERNAME.github.io/mein-neues-projekt/ online.

Danach läuft jede Änderung wie gewohnt: **speichern → Commit → Sync Changes**.

**Weg B: Projekt ohne GitHub**

1.  Ordner anlegen und in VSCodium öffnen (wie Schritte 1–2 oben).

2.  Dateien anlegen und mit **Go Live** ansehen.

3.  Optional: In Source Control auf **Initialize Repository** klicken, um einen lokalen Versionsverlauf zu haben (Kapitel 7).

So arbeiten auch die Schüler. Später lässt sich jedes Projekt mit **Publish to GitHub** nachträglich veröffentlichen.

## Kapitel 10: Ein Projekt an mehreren Orten bearbeiten

Ein GitHub-Projekt lässt sich in VSCodium, VS Code, VS Code im Browser (vscode.dev, github.dev) und auf mehreren Rechnern bearbeiten, z. B. in der Schule und zu Hause. GitHub ist dabei die zentrale Ablage, alle anderen sind Kopien davon.

**Die goldene Regel**

1.  **Vor dem Arbeiten:** In Source Control auf **Sync Changes** klicken (oder unten links auf das Kreispfeil-Symbol). So holst du die neueste Version von GitHub.

2.  **Nach dem Arbeiten:** speichern → **Commit** → **Sync Changes**. So liegt deine Arbeit wieder auf GitHub.

Wer sich daran hält, hat überall denselben Stand.

**Ein bestehendes GitHub-Projekt in VSCodium holen:** Strg + Shift + P → Git: Clone → **Clone from GitHub** → Repository auswählen → Speicherort wählen → **Open** (Kapitel 8).

**Wenn es doch kollidiert:** Wurde dieselbe Zeile an zwei Orten geändert, ohne zwischendurch zu synchronisieren, meldet VSCodium einen **Merge-Konflikt**. In der Datei erscheinen dann beide Versionen mit den Knöpfen *Accept Current Change*, *Accept Incoming Change* und *Accept Both Changes*. Die gewünschte Version anklicken, speichern, dann Commit und Sync.

**Gut zu wissen:** Bei *vscode.dev* oder *github.dev* im Browser wird beim Commit direkt auf GitHub gespeichert. In GitHub *Codespaces* braucht es wie in VSCodium zusätzlich **Sync**. Einstellungen und Extensions von VS Code und VSCodium sind getrennt und müssen in beiden eingerichtet werden (siehe „Vorab: Welcher Editor?“).

## Kapitel 11: CSS – das erste Stylesheet

*Grundlage: Peter Müller, „Einstieg in HTML und CSS“, Kapitel 3.*

HTML legt fest, **was** auf der Seite steht. **CSS** (*Cascading Style Sheets*) legt fest, **wie** es aussieht: Farben, Schriften, Abstände. Die Gestaltung steht in einer eigenen Datei, dem **Stylesheet**.

**Gut zu wissen:** Jeder Browser hat ein eingebautes Stylesheet. Deshalb sind Überschriften auch ohne eigenes CSS groß und fett, und der Hintergrund ist weiß. Eigene CSS-Regeln überschreiben diese Vorgaben.

**1. Ordner und Datei anlegen**

1. Im Projektordner (dort, wo die Startseite `index.html` liegt) einen Ordner `css` anlegen.
2. Darin eine neue Datei `style.css` anlegen.

```
meine-erste-website/
├── index.html
└── css/
    └── style.css
```

Der Name `style.css` ist üblich, aber nicht Pflicht. Wichtig ist die Endung `.css` und ein Name nach den üblichen Regeln (klein, ohne Leerzeichen und Umlaute).

**2. HTML und CSS verbinden mit `<link>`**

In der `index.html` im `<head>`, direkt vor `</head>`, eine Zeile einfügen:

```html
<link href="css/style.css" rel="stylesheet">
```

| Attribut | Bedeutung |
|---|---|
| `href="css/style.css"` | Pfad zum Stylesheet (relativ, wie bei Bildern und Links) |
| `rel="stylesheet"` | *relation*: „Die verknüpfte Datei ist ein Stylesheet.“ |

Nach diesem Schritt ändert sich im Browser noch nichts, die Verbindung steht aber.

**Übungsseiten in Unterordnern** brauchen den Pfad mit `../`, z. B. `uebungen/01-erste-seite/index.html`:

```html
<link href="../../css/style.css" rel="stylesheet">
```

**3. Ein Kommentar am Anfang**

In CSS stehen Kommentare zwischen `/*` und `*/` (in HTML dagegen `<!-- … -->`):

```css
/* Stylesheet für meine erste Website */
```

**4. Die erste CSS-Regel: Farben für die ganze Seite**

```css
body {
  background-color: floralwhite;
  color: black;
}
```

**5. Den Kopfbereich gestalten**

```css
header {
  background-color: steelblue;
  color: white;
  padding: 1rem;
}
```

`padding` ist der **Innenabstand** zwischen Text und Rand. Bei `1rem` kein Leerzeichen zwischen Zahl und Einheit.
Diese Regel wirkt nur, wenn es in der HTML-Datei ein `<header>`-Element gibt.

**Der Aufbau einer CSS-Regel**

```
selektor {
  eigenschaft: wert;
}
```

| Begriff | Beispiel | Bedeutung |
|---|---|---|
| Selektor | `body` | **welches** HTML-Element gestaltet wird |
| Deklarationsblock | `{ … }` | alles zwischen den geschweiften Klammern |
| Deklaration | `color: black;` | eine Anweisung: Eigenschaft + Wert |
| Eigenschaft | `color` | **was** geändert wird (englisch, amerikanische Schreibweise: `color`, nicht `colour`) |
| Wert | `black` | **wie** es aussehen soll |

Jede Deklaration endet mit einem **Strichpunkt** `;`. Geschweifte Klammern: Windows **AltGr + 7 / 0**, macOS **Option + 8 / 9**.

**Farben:** Für den Anfang reichen englische Farbnamen (`black`, `white`, `whitesmoke`, `steelblue`, `floralwhite` …). Liste: https://www.w3schools.com/colors/colors_names.asp. Auf **ausreichend Kontrast** zwischen Hintergrund und Schrift achten.

**CSS im Browser untersuchen:** Rechtsklick auf ein Element → **Untersuchen**. Rechts im Bereich **Stile** sieht man, welche CSS-Regeln wirken, auch die des Browser-Stylesheets (*user agent stylesheet*). Werte lassen sich dort testweise ändern; das ändert aber nicht die Datei.

**Ergebnis prüfen:** Stylesheet speichern und die **HTML-Datei** (nicht die CSS-Datei) im Browser bzw. mit **Go Live** ansehen.

**Wirkt das CSS nicht?** Häufige Ursachen:

- **Tippfehler im `<link>`**, z. B. `rel=""stylesheet"` (doppeltes Anführungszeichen) – dann ist `rel` leer und der Browser ignoriert die Datei.
- **Falscher Pfad** in `href` (Ordner heißt `CSS` statt `css`, `../` fehlt in Unterordnern).
- **Stylesheet nicht gespeichert** (weißer Punkt im Tab).
- **Doppelpunkt oder Strichpunkt fehlt**, oder eine geschweifte Klammer ist nicht geschlossen.
- Prüfen mit den Entwicklerwerkzeugen: Taucht `style.css` unter **Stile** nicht auf, ist die Verbindung kaputt.

## Anhang: Häufige Probleme und Spickzettel

| Problem                             | Lösung                                                                                |
|-------------------------------------|---------------------------------------------------------------------------------------|
| Änderung erscheint nicht im Browser | Datei speichern (Strg + S), weißer Punkt im Tab muss weg sein                         |
| „Go Live“ fehlt unten rechts        | Live Server installiert? Eine .html-Datei im Editor öffnen; ggf. VSCodium neu starten |
| ! + Enter erzeugt kein Grundgerüst  | Datei muss auf .html enden; das ! muss allein in der ersten Zeile stehen              |
| CSS wirkt nicht                     | `<link href="css/style.css" rel="stylesheet">` genau prüfen (Anführungszeichen, Pfad), Stylesheet speichern (Kapitel 11) |
| Explorer links ist leer             | Über File → Open Folder… den Projektordner öffnen, nicht nur eine Datei               |
| Extension-Suche findet nichts       | Internetverbindung bzw. Freigabe von open-vsx.org im Schulnetz prüfen                 |
| Unterseite geht online, lokal nicht | Link zeigt auf einen Ordner (`…/`) → `index.html` ergänzen, z. B. `ordner/index.html` (Kapitel 4) |

**Tastenkürzel**

| Kürzel           | Wirkung                                        |
|------------------|------------------------------------------------|
| Strg + S         | Speichern                                      |
| Strg + Z         | Rückgängig                                     |
| Strg + Shift + P | Befehlspalette: jede Funktion per Suche finden |
| Strg + Ö         | Terminal ein-/ausblenden                       |
| Strg + B         | Seitenleiste ein-/ausblenden                   |
| Strg + /         | Zeile auskommentieren                          |
| Alt + Shift + F  | Code automatisch formatieren                   |
