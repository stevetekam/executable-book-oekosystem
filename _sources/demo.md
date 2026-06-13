# **Praxisbeispiele**

:::{note}
**CommonMark & GFM live erleben**

Diese Seite demonstriert den gesamten Workflow von der ersten
Markdown-Datei bis zur fertigen Website. Alle Beispiele sind
direkt in diesem Buch sichtbar und nachvollziehbar.
:::

---

## **1. Der vollständige Workflow**

So entsteht dieses Buch Schritt für Schritt:

1. Markdown-Dateien schreiben
2. `_toc.yml` Struktur definieren
3. `_config.yml` Buch konfigurieren
4. `jb build .` Jupiter Book bauen
5. Fertige HTML-Webseite in `build/html/`

### **Die Verzeichnisstruktur meines Buchs**

1. `_config.yml`   <- Titel, Autor, Logo
2. `_toc.yml`      <- Inhaltsverzeichnis
3. `intro.md`      <- Startseite
4. `commonmark.md` <- Kapitel 1
5. `gfm.md`        <- Kapitel 2
6. `demo.md`       <- Seite für Praxisbeispiele 
7. `_build/`       <- Book wird gebaut
8. `html/`         <- HTML Datei
9. `index.html`    <- Fertige Webseite

### **Build-Befehle im Überblick**

````bash
# **Neues Buch erstellen**
jb create mein-buch

# **HTML bauen**
jb build .

# **Build-Verzeichnis leeren**
jb clean .

# **PDF bauen**
jb build . --builder pdflatex
````

---

## **2. CommonMark Syntax**

### **Überschriften**

````markdown
# H1 – Haupttitel
## H2 – Abschnitt
### H3 – Unterabschnitt
#### H4 – Unterunterabschnitt
````

---

### **Textformatierung**

````markdown
**fetter Text**
*kursiver Text*
***fett und kursiv***
`Zeile von Code`
````

**Ergebnis:**

**fetter Text**  *kursiver Text*  ***fett und kursiv***  `Zeile von Code`

---

### **Listen**

````markdown
- Erster Punkt
- Zweiter Punkt
  - Eingerückter Unterpunkt
  - Noch ein Unterpunkt
- Dritter Punkt
````

**Ergebnis:**

- Erster Punkt
- Zweiter Punkt
  - Eingerückter Unterpunkt
  - Noch ein Unterpunkt
- Dritter Punkt

---

### **Blockzitat**

````markdown
> CommonMark ist die präzise, eindeutige Spezifikation von Markdown.
> Sie bildet das Fundament des gesamten Executable Book Ökosystems.
````

**Ergebnis:**

> CommonMark ist die präzise, eindeutige Spezifikation von Markdown.
> Sie bildet das Fundament des gesamten Executable Book Ökosystems.

---

### **Codeblock**

````markdown
```python
# **Ein einfaches Python-Beispiel**
namen = ["CommonMark", "GFM", "MyST", "Jupyter Book"]

for name in namen:
    print(f"Werkzeug: {name}")
```
````

**Ergebnis:**

````python
# **Ein einfaches Python-Beispiel**
namen = ["CommonMark", "GFM", "MyST", "Jupyter Book"]

for name in namen:
    print(f"Werkzeug: {name}")
````

---

### **Links und Bilder**

````markdown
[CommonMark Spezifikation](https://commonmark.org)
[GFM Spezifikation](https://github.github.com/gfm/)
[Executable Books Projekt](https://executablebooks.org)
````

**Ergebnis:**

- [CommonMark Spezifikation](https://commonmark.org)
- [GFM Spezifikation](https://github.github.com/gfm/)
- [Executable Books Projekt](https://executablebooks.org)

---

## **3. GFM Erweiterungen**

### **Tabelle**

````markdown
| **Standard** | **Erscheinungsjahr** | **Basis**   |
|:-------------|:--------------------:|------------:|
| Markdown     | 2004                 | –           |
| CommonMark   | 2014                 | Markdown    |
| GFM          | 2017                 | CommonMark  |
| MyST         | 2020                 | CommonMark  |
````

**Ergebnis:**

| **Standard** | **Erscheinungsjahr** | **Basis**       |
|:-------------|:----------------:|------------:|
| Markdown     | 2004             | –           |
| CommonMark   | 2014             | Markdown    |
| GFM          | 2017             | CommonMark  |
| MyST         | 2020             | CommonMark  |

---

### **Task-Liste**

````markdown
- [x] Markdown-Grundlagen verstehen
- [x] CommonMark Spezifikation kennen
- [x] GFM Erweiterungen beherrschen
- [ ] Eigenes Jupyter Book veröffentlichen
````

**Ergebnis:**

- [x] Markdown-Grundlagen verstehen
- [x] CommonMark Spezifikation kennen
- [x] GFM Erweiterungen beherrschen
- [ ] Eigenes Jupyter Book veröffentlichen

---

### **Durchstreichen**

````markdown
~~Markdown hat keine eindeutige Spezifikation~~ CommonMark löst dieses Problem.
~~GFM ist nur für GitHub~~ GFM wird auf vielen Plattformen verwendet.
````

**Ergebnis:**

~~Markdown hat keine eindeutige Spezifikation~~ CommonMark löst dieses Problem.

~~GFM ist nur für GitHub~~ GFM wird auf vielen Plattformen verwendet.

---

### **Syntax im Terminal**

````markdown
```bash
# **System aktualisieren**
sudo apt update && sudo apt upgrade

# **Jupyter Book bauen**
cd ~/c/executable-book-oekosystem
jb build .
```
````

**Ergebnis:**

````bash
# **System aktualisieren**
sudo apt update && sudo apt upgrade

# **Jupyter Book bauen**
cd ~/c/executable-book-oekosystem
jb build .
````

---

## **4.Hinweisboxen**

In GFM ist möglich Hinweisboxen zu integrieren:

````markdown
```{note}
Das ist ein blauer Hinweis.
```

```{tip}
Das ist ein grüner Tipp.
```

```{warning}
Das ist eine orange Warnung.
```

```{important}
Das ist eine lila wichtige Information.
```
````

**Ergebnis:**

:::{note}
Das ist ein blauer Hinweis.
:::

:::{tip}
Das ist ein grüner Tipp.
:::

:::{warning}
Das ist eine orange Warnung.
:::

:::{important}
Das ist eine lila wichtige Information.
:::

---

## **5. Navigation zwischen Kapiteln**

Die Navigation
zwischen Kapiteln ist wichtig, da es einen schnellen Zugriff zu anderen Kapitel ermöglicht.

````markdown
Zurück zu {doc}`commonmark` für die Grundlagen.
Weiter zu {doc}`gfm` für die Erweiterungen.
````

**Ergebnis:**

Zurück zu {doc}`commonmark` für die Grundlagen.
Weiter zu {doc}`gfm` für die Erweiterungen.

---

## **Zusammenfassung**

:::{important}
**Was wir gelernt haben**

- **CommonMark** liefert die eindeutige, standardisierte Basis
- **GFM** erweitert CommonMark um Tabellen, Task-Listen,
  Durchstreichen und Syntax in Terminal 
- **Jupyter Book** baut aus diesen Dateien eine professionelle Website
- Einfach im Terminal schreiben -> `jb build .` -> Fertig
:::

---

## **Verbindung zu anderen Kapiteln**

:::{note}
**Navigation im Buch**

- {doc}`commonmark`  Der offizielle Markdown-Standard
- {doc}`gfm`  GitHub-Flavored Markdown im Detail
:::

---

## **Quellen & Weiterführende Literatur**

| **Ressource** | **Beschreibung** | **Link** |
|-----------|--------------|------|
| CommonMark  | Offizielle Spezifikation | [commonmark.org](https://commonmark.org) |
| GFM Spezifikation | GitHub Flavored Markdown | [github.github.com/gfm](https://github.github.com/gfm/) |
| Executable Books | Das Ökosystem | [executablebooks.org](https://executablebooks.org) |


```{tableofcontents}
```
