# MyST Markdown

:::{note}
**Markedly Structured Text:  Markdown für die Wissenschaft**

MyST erweitert CommonMark um mächtige Werkzeuge für wissenschaftliches
Publizieren: Direktiven, Rollen, Querverweise, Gleichungen und Zitationen,
alles in reinem Markdown.
:::

---

## 1. Was ist MyST Markdown?

MyST (Markedly Structured Text) ist darauf ausgelegt, publikationsreife
Dokumente vollständig in Markdown zu erstellen. Die Erweiterungen und das
Design von MyST sind vom Sphinx- und reStructuredText-Ökosystem inspiriert
und stellen eine Obermenge von CommonMark dar. 

In Juni 2024 wurde MyST Markdown offiziell Teil von Project Jupyter. 

:::{tip}
**Offizielle Ressourcen**
- Dokumentation: [mystmd.org/guide](https://mystmd.org/guide)
- Spezifikation: [mystmd.org/spec](https://mystmd.org/spec)
- Syntax-Übersicht: [mystmd.org/guide/syntax-overview](https://mystmd.org/guide/syntax-overview)
:::

---

## 2. MyST im Ökosystem

MyST steht im Zentrum des Executable Book Ökosystems:

| Ebene | Werkzeug | Rolle |
|---|---|---|
| Syntax | **CommonMark** | Basis-Markdown |
| Erweiterung | **MyST Markdown** | Wissenschaftliche Syntax |
| Parser | **MyST-Parser** | Übersetzt MyST → Sphinx AST |
| Build | **Sphinx** | Erzeugt HTML, PDF, ePub |
| Publisher | **Jupyter Book** | Orchestriert alles |

---

## 3. Direktiven: Block-Level-Erweiterungen

Direktiven sind Block-Level-Erweiterungspunkte wie Hinweisboxen,
Tabs, Abbildungen oder eingebettete Charts. 

Die allgemeine Syntax lautet:

````markdown
```{direktiven-name} Argument
:option: wert

Inhalt der Direktive
```
````

### 3.1 Hinweisboxen

````markdown
```{note}
Das ist ein Hinweis.
```

```{warning}
Das ist eine Warnung.
```

```{tip}
Das ist ein Tipp.
```
````
Ergebnis:

:::{note}
Das ist ein Hinweis
:::

:::{warning}
Das ist eine Warnung
:::

:::{tip}
Das ist ein Tipp
:::


Verfügbare Typen und ihre Farben:

| Direktive | Farbe | Verwendung |
|---|---|---|
| `note` | blau | Allgemeine Hinweise |
| `tip` | grün | Hilfreiche Tipps |
| `important` | lila | Wichtige Information |
| `warning` | orange | Warnungen |
| `danger` | rot | Kritische Warnungen |
| `seealso` | grau | Weiterführende Links |

### 3.2 Abbildungen mit Beschriftung

````markdown
```{figure} https://upload.wikimedia.org/wikipedia/commons/3/35/Tux.svg
:width: 300px
:align: center
:name: linux-logo

Das Linux Logo.
```
````
Ergebnis:

```{figure} https://upload.wikimedia.org/wikipedia/commons/3/35/Tux.svg
:width: 300px
:align: center
:name: linux-logo

Das Linux Logo.
```


---

## 4. Rollen: Inline-Erweiterungen

Rollen sind Inline-Erweiterungspunkte für Komponenten wie
Querverweise, externe Referenzen, Zitationen oder Inline-Mathematik.
Rollen und Direktiven sind zwei der mächtigsten Teile von MyST.
Sie funktionieren wie Funktionen, aber in einer Auszeichnungssprache. 

Die Syntax lautet: `` {rollenname}`Inhalt` ``

### Wichtige Rollen im Überblick

| Rolle | Beispiel | Funktion |
|---|---|---|
| `doc` | `` {doc}`commonmark` `` | Link zu einer anderen Seite |
| `ref` | `` {ref}`mein-label` `` | Link zu einem Label |
| `eq` | `` {eq}`meine-gleichung` `` | Referenz auf Gleichung |
| `math` | `` {math}`E = mc^2` `` | Inline-Mathematik |
| `abbr` | `` {abbr}`MyST (Markedly Structured Text)` `` | Abkürzung |

---

## 5. Mathematische Formeln

Mathematik kann entweder inline oder als Gleichungsblock
dargestellt werden. Neben der üblichen MyST-Syntax kann auch
„Dollar-Math" verwendet werden, abgeleitet von LaTeX: Inline-Mathematik
wird mit einfachen Dollarzeichen umschlossen ($), Gleichungsblöcke
mit zwei Dollarzeichen ($$). 

### 5.1 Inline-Mathematik

````markdown
Die Formel $E = mc^2$ beschreibt die Masse-Energie-Äquivalenz.
````

Ergebnis: Die Formel $E = mc^2$ beschreibt die Masse-Energie-Äquivalenz.

### 5.2 Gleichungsblöcke

````markdown
$$
\int_{-\infty}^{\infty} e^{-x^2} dx = \sqrt{\pi}
$$
````

Ergebnis:

$$
\int_{-\infty}^{\infty} e^{-x^2} dx = \sqrt{\pi}
$$

### 5.3 Nummerierte Gleichung mit Label

````markdown
```{math}
:label: bayes-theorem

P(A|B) = \frac{P(B|A) \cdot P(A)}{P(B)}
```
````

Referenz im Text: `` {eq}`bayes-theorem` ``

Ergebnis:

```{math}
:label: bayes-theorem

P(A|B) = \frac{P(B|A) \cdot P(A)}{P(B)}
```
---

## 6. Querverweise zwischen Seiten

MyST unterstützt reichhaltige Informationen für das Verlinken
zu anderen Dokumenten in gängigen Diensten wie Wikipedia oder
Digital Object Identifier(DOI)-Links. Dies ermöglicht Vorschauen sowie einfache
Einbindung von Zitationen. 

### Verweis auf andere Kapitel dieses Buchs

````markdown
Siehe {doc}`commonmark` für die Grundlagen.
Weiter mit {doc}`jupyterbook` für den Build-Prozess.
````
Ergebnis:

Siehe {doc}`commonmark` für die Grundlagen.
Weiter mit {doc}`jupyterbook` für den Build-Prozess.


### Verweis auf ein Label

````markdown
(mein-abschnitt)=
## Mein Abschnitt

... später im Text ...

Siehe {ref}`mein-abschnitt`.
````

---

## 7. Zitationen

Wenn eine lokale Zitationsliste als BibTeX-Datei (*.bib) vorhanden
ist, können die Schlüssel mit einer an LaTeX angelehnten Syntax
referenziert werden: `{cite:p}` erzeugt eine Klammer-Zitation,
`{cite:t}` eine textuelle Zitation. Die Zitationen erscheinen
inline und erzeugen automatisch einen Literaturabschnitt am Ende der Seite. 

````markdown
Wie in {cite:p}`jupyterbook2021` beschrieben ...
````

---

## 8. Frontmatter: Metadaten für wissenschaftliche Artikel

Frontmatter erlaubt es, Metadaten über eine Seite anzugeben,
einschließlich Titel, Thumbnail, Autoren und
wissenschaftliche Identifikatoren wie DOI. 

````yaml
---
title: Mein wissenschaftlicher Artikel
date: 2025-01-15
authors:
  - name: Max Mustermann
    affiliations:
      - HAW Landshut
doi: 10.1234/beispiel
---
````

---

## 9. MyST Markdown  vs. GitHub-Flavored Markdown (GFM)

| Feature | GFM | MyST |
|---|---|---|
| Tabellen | ✅ | ✅ |
| Codeblöcke | ✅ | ✅ |
| Mathematik (LaTeX) | ❌ | ✅ |
| Direktiven | ❌ | ✅ |
| Rollen | ❌ | ✅ |
| Querverweise | ❌ | ✅ |
| Zitationen (BibTeX) | ❌ | ✅ |
| Frontmatter/Metadaten | ❌ | ✅ |
| Nummerierte Gleichungen | ❌ | ✅ |

---

## Verbindung zu anderen Kapiteln

:::{important}
**Navigation im Buch**

- {doc}`commonmark`  Die Basis, auf der MyST aufbaut
- {doc}`jupyterbook`  Nutzt MyST als primäre Eingabesprache
- {doc}`sphinx`  Verarbeitet den MyST-AST als Build-Backend
- {doc}`demo`  Praktische MyST-Beispiele zum Ausprobieren
:::

---

## Quellen & Weiterführende Literatur

| Ressource | Beschreibung | Link |
|---|---|---|
| MyST Dokumentation | Offizielle Dokumentation | [mystmd.org/guide](https://mystmd.org/guide) |
| MyST Spezifikation | Formelle Spezifikation | [mystmd.org/spec](https://mystmd.org/spec) |
| Jupyter Book MyST | MyST in Jupyter Book | [jupyterbook.org](https://jupyterbook.org/stable/authoring/mystmd/) |
| MyST Math | Mathematik in MyST | [mystmd.org/guide/math](https://mystmd.org/guide/math) |
| Executable Books Blog | MyST wird Teil von Jupyter | [executablebooks.org](https://executablebooks.org/en/latest/blog/2024-05-20-jupyter-book-myst/) |
| SciPy Proceedings 2024 | MyST in der Wissenschaft | [proceedings.scipy.org](https://proceedings.scipy.org/articles/NKVC9349) |
