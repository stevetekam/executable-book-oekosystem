# Jupyter Book

:::{note}
**Von der Markdown-Datei zum professionellen Buch**

Jupyter Book ist das zentrale Werkzeug des Executable Book Ökosystems.
Es orchestriert MyST Markdown, Jupyter Notebooks, Sphinx und LaTeX zu
einer einzigen, reproduzierbaren Publikationspipeline.
:::

---

## 1. Was ist Jupyter Book?

Jupyter Book ist ein Command-Line-Interface zum Erstellen schöner,
publikationsreifer Bücher und Dokumente aus rechnerischen Inhalten,
ein Kernprojekt des Executable Books Project, einer internationalen
Zusammenarbeit zum Aufbau von Open-Source-Werkzeugen für
reproduzierbare wissenschaftliche Publikationen. 

Seit seiner Veröffentlichung im Jahr 2020 hat sich Jupyter Book zu
einem weit verbreiteten Werkzeug in der Computerwissenschaft und im
Open Publishing entwickelt und betreibt über 18.000 öffentlich
zugängliche Bücher, Vorlesungen, Tutorials und Wissensrepositorien. 

:::{tip}
**Offizielle Ressourcen**
- Dokumentation: [jupyterbook.org](https://jupyterbook.org)
- GitHub: [github.com/executablebooks/jupyter-book](https://github.com/executablebooks/jupyter-book)
- Galerie: [executablebooks.org/en/latest/gallery](https://executablebooks.org/en/latest/gallery/)
:::

---

## 2. Geschichte

Im Jahr 2020 wurde das neue Jupyter Book (Version 0.7) angekündigt,
das Jupyter Book von Grund auf neu aufbaute, um es einfacher zu
installieren, schneller zu nutzen und komplexere Publikationsinhalte
zu ermöglichen. Mit diesem Schritt zu Sphinx wurde der neue
Markdown-Dialekt MyST Markdown geschaffen, der die Ausdruckskraft
von Sphinx's reStructuredText mit der Vertrautheit und Lesbarkeit
von Markdown verbindet. 

Im Jahr 2023 wurde MyST als Top-Level-Projekt in Executable Books
anerkannt. Mit MyST-MD wurde eine kritische neue Fähigkeit
hinzugefügt: eine Dokumentstruktur und -engine, die MyST-Dokumente
in einem flexiblen und wiederverwendbaren Format (JSON) bereitstellt. 

### Zeitlinie

| Jahr | Ereignis |
|------|----------|
| 2019 | Erste Version von Jupyter Book |
| 2020 | Neuaufbau auf Basis von Sphinx + MyST (v0.7) |
| 2022 | Start von MyST-MD (JavaScript-Engine) |
| 2023 | MyST wird Top-Level-Projekt in Executable Books |
| 2024 | Jupyter Book 2: Aufbau auf MyST Document Engine |

---

## 3. Die drei Kerndateien

Es gibt drei Dinge, die zum Erstellen eines Jupyter Books benötigt werden:
eine Sammlung von Notebook- und Markdown-Dateien als Inhalte,
eine `_toc.yml`-Datei, die die Struktur des Buchs definiert,
und eine `_config.yml`-Datei für die Konfiguration.

### 3.1 `_config.yml`: Die Konfigurationsdatei

Alle Konfigurationen für das Buch befinden sich in einer YAML-Datei
namens `_config.yml`. Dort können Metadaten wie Titel und Logo
definiert, interaktive Schaltflächen aktiviert und das
Ausführungsverhalten von Notebooks gesteuert werden. 

````yaml
# _config.yml
title: Das Executable Book Ökosystem
author: Max Mustermann
logo: logo.png

execute:
  execute_notebooks: "off"

bibtex_bibfiles:
  - references.bib
````

### 3.2 `_toc.yml`: Das Inhaltsverzeichnis

Die Struktur des Buchs wird durch eine Table of Contents-Datei
bestimmt. Dies ist eine YAML-Datei (`_toc.yml`), die eine Struktur
definiert, die Jupyter Book verwendet, um die Reihenfolge und
Verschachtelung der Seiten zu erstellen. 

**Einfache Struktur:**
````yaml
format: jb-book
root: intro
chapters:
- file: kapitel1
- file: kapitel2
````

**Mit Teilen und Abschnitten:**
````yaml
format: jb-book
root: intro
parts:
  - caption: Teil 1  Grundlagen
    chapters:
    - file: commonmark
    - file: myst
  - caption: Teil 2  Werkzeuge
    chapters:
    - file: jupyterbook
    - file: sphinx
````

---

## 4. Der Build-Prozess

Derzeit werden zwei Arten von Ausgaben unterstützt: eine
HTML-Website für das Buch und ein PDF, das aus dem Buch-HTML
erstellt wird. Das Standardausgabeformat ist HTML. 

### 4.1 HTML bauen

````bash
# Buch erstellen
jb create mein-buch

# HTML bauen
jb build mein-buch

# Ergebnis öffnen
# file:///pfad/zu/mein-buch/_build/html/index.html
````

### 4.2 PDF bauen

````bash
# PDF über LaTeX
jb build mein-buch --builder pdflatex

# PDF über HTML (einfacher)
jb build mein-buch --builder pdfhtml
````

### 4.3 Weitere Build-Befehle

| Befehl | Funktion |
|--------|----------|
| `jb build .` | Buch im aktuellen Verzeichnis bauen |
| `jb clean .` | Build-Verzeichnis leeren |
| `jb create mein-buch` | Neues Buch-Template erstellen |
| `jb toc .` | `_toc.yml` automatisch generieren |
| `jb --version` | Versionsnummer anzeigen |

---

## 5. Unterstützte Dateitypen

| Dateityp | Endung | Beschreibung |
|----------|--------|--------------|
| Markdown | `.md` | MyST oder CommonMark |
| Jupyter Notebook | `.ipynb` | Code + Text |
| reStructuredText | `.rst` | Sphinx-nativer Format |
| MyST Notebook | `.md` mit Kernel | Markdown als Notebook |

---

## 6. Interaktivität: Notebooks im Buch

Einer der größten Vorteile von Jupyter Book ist die nahtlose
Integration von Jupyter Notebooks. Code wird beim Build ausgeführt
und die Ergebnisse direkt in die Seite eingebettet:

````markdown
```{code-cell} python
import matplotlib.pyplot as plt
import numpy as np

x = np.linspace(0, 2 * np.pi, 100)
plt.plot(x, np.sin(x))
plt.title("Sinusfunktion")
plt.show()
```
````
Ergebnis: 

```{code-cell} python
import matplotlib.pyplot as plt
import numpy as np

x = np.linspace(0, 2 * np.pi, 100)
plt.plot(x, np.sin(x))
plt.title("Sinusfunktion")
plt.show()
```


Die Ausführung lässt sich in `_config.yml` steuern:

````yaml
execute:
  execute_notebooks: "force"   # immer ausführen
  # execute_notebooks: "cache" # nur bei Änderungen
  # execute_notebooks: "off"   # nie ausführen
````

---

## 7. Jupyter Book 2:  Die Zukunft

Jupyter Book 2 ist nun ein Jupyter-Subprojekt und betreibt bereits
mehrere offene wissenschaftliche Ressourcen, darunter The Turing Way,
QuantEcon, Project Pythia und das QIIME 2 Framework. Es ermöglicht
Forschern, hochwertige interaktive Inhalte zu veröffentlichen,
mit Unterstützung für Websites, Typst, PDF, LaTeX, Microsoft Word
und JATS XML. 

---

## Verbindung zu anderen Kapiteln

:::{important}
**Navigation im Buch**

- {doc}`commonmark` Das Markdown-Fundament von Jupyter Book
- {doc}`myst`  Die Auszeichnungssprache, die Jupyter Book verwendet
- {doc}`sphinx`  Das Build-Backend hinter Jupyter Book
- {doc}`demo`  Ein vollständiges Jupyter Book Beispiel in der Praxis
:::

---

## Quellen & Weiterführende Literatur

| Ressource | Beschreibung | Link |
|-----------|--------------|------|
| Jupyter Book Doku | Offizielle Dokumentation | [jupyterbook.org](https://jupyterbook.org) |
| Executable Books | Das übergeordnete Projekt | [executablebooks.org](https://executablebooks.org) |
| Jupyter Book 2 | Nächste Generation | [next.jupyterbook.org](https://next.jupyterbook.org) |
| Galerie | Beispielbücher aus der Community | [executablebooks.org/gallery](https://executablebooks.org/en/latest/gallery/) |
| SciPy 2025 Paper | Jupyter Book 2 Architektur | [proceedings.scipy.org](https://proceedings.scipy.org/articles/hwcj9957) |
| Zenodo DOI | Zitierbarer Verweis | [doi.org/10.5281/zenodo.2561065](https://doi.org/10.5281/zenodo.2561065) |
