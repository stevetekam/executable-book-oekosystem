# **CommonMark**

:::{note}
**Der offizielle Markdown-Standard**

CommonMark ist die präzise, eindeutige Spezifikation von Markdown –
das Fundament, auf dem GitHub-Flavored Markdown, MyST und das gesamte
Executable Book Ökosystem aufbauen.
:::

---

## **1. Die Entstehung von Markdown**

Markdown wurde 2004 von **John Gruber** in Zusammenarbeit mit **Aaron Swartz**
entwickelt. Die Idee war einfach: lesbarer Klartext, der sich automatisch
in HTML übersetzen lässt.

Im Jahr 2008 übernahm GitHub Markdown für README-Dateien – ein entscheidender
Schritt für die weltweite Verbreitung.

:::{tip}
**Originale Quellen**
- John Gruber's originale Markdown-Beschreibung: [daringfireball.net/projects/markdown](https://daringfireball.net/projects/markdown/)
- Wikipedia: [en.wikipedia.org/wiki/Markdown](https://en.wikipedia.org/wiki/Markdown)
:::

---

## **2. Das Problem: Fragmentierung**

Das ursprüngliche Markdown hatte ein grundlegendes Problem:
**keine eindeutige Spezifikation.**

John Gruber's originale Beschreibung ließ viele Fragen offen:

- Was passiert bei verschachtelten Listen?
- Wie werden mehrdeutige Leerzeichen behandelt?
- Wie verhalten sich Links in bestimmten Kontexten?

Das Ergebnis: Jede Plattform implementierte Markdown leicht anders.
Dasselbe Dokument sah auf GitHub, Stack Overflow und Reddit
unterschiedlich aus.

---

## **3. Die Geburt von CommonMark (2014)**

Im Jahr 2014 startete eine Gruppe von Entwicklern die Standardisierung.
Zu den Initiatoren gehörten:

| **Person** | **Rolle** |
|--------|-------|
| **John MacFarlane** | Philosoph, Erfinder von Pandoc |
| **Jeff Atwood** | Mitgründer von Stack Overflow |
| Vertreter von GitHub | – |
| Vertreter von Reddit | – |
| Vertreter von Stack Exchange | – |

Das Projekt hieß zunächst **„StandardMark"**. John Gruber lehnte diesen
Namen ab – woraufhin es in **CommonMark** umbenannt wurde.

:::{important}
CommonMark bietet eine eindeutige Spezifikation mit über
**500 Konformitätstests**, die sicherstellen, dass jede Implementierung
identische Ergebnisse liefert.
:::

**Offizielle Ressourcen:**
- Spezifikation: [commonmark.org](https://commonmark.org)
- Interaktives Tutorial: [commonmark.org/help/tutorial](https://commonmark.org/help/tutorial/)
- Live-Demo (Dingus): [spec.commonmark.org/dingus](https://spec.commonmark.org/dingus/)
- Babelmark – Vergleich aller Implementierungen: [babelmark.github.io](https://babelmark.github.io)

---

## **4. CommonMark vs. originales Markdown**

| **Merkmal** | **Originales Markdown (2004)** | **CommonMark** |
|---------|---------------------------|------------|
| Spezifikation | Informal, mehrdeutig | Formell, präzise |
| Konformitätstests | Keine | 500+ |
| Verhalten | Implementierungsabhängig | Einheitlich definiert |
| Aktuelle Version | 1.0 (2004, eingefroren) | 0.31.2 (Januar 2024) |
| Medientyp | – | `text/markdown; variant=CommonMark` |
| Pflege | Nicht aktiv | Aktiv gepflegt |

---

## **5. CommonMark Syntax: Die Grundbausteine**

### **5.1 Überschriften**

````markdown
# H1 – Haupttitel
## H2 – Abschnitt
### H3 – Unterabschnitt
#### H4 – Unterunterabschnitt
````

### **5.2 Textformatierung**

````markdown
**fett**        -> fett
*kursiv*        -> kursiv
***fett+kursiv*** -> fett und kursiv
`code`          -> inline Code
~~durchgestrichen~~ -> durchgestrichen
````

### **5.3 Listen**

````markdown
- Ungeordnete Liste
- Zweiter Punkt
  - Eingerückter Punkt

1. Geordnete Liste
2. Zweiter Punkt
3. Dritter Punkt
````

### **5.4 Links und Bilder**

````markdown
[Linktext](https://commonmark.org)
![Bildbeschreibung](pfad/zum/bild.png)
````

### **5.5 Codeblöcke**

````markdown
```python
def hallo():
    print("Hello, CommonMark!")
```
````

### **5.6 Blockzitate**

````markdown
> Das ist ein Blockzitat.
> Es kann mehrere Zeilen umfassen.
>
````

### **5.7 Horizontale Linie**

````markdown
---
````

---

## **6. Warum CommonMark das Fundament ist**

CommonMark löst drei grundlegende Probleme:

**Eindeutigkeit:** Gleicher Input, gleicher Output auf jeder Plattform.

**Versionskontrolle:**  Reiner Klartext ist ideal für Git: diffs sind
lesbar, Konflikte lösbar, Geschichte nachvollziehbar.

**Interoperabilität:**  Alle modernen Werkzeuge bauen darauf auf:
GitHub, GitLab, Jupyter, Pandoc, MyST, Sphinx und viele mehr.

---

## **Verbindung zu anderen Kapiteln**

:::{important}
**Navigation im Buch**

- {doc}`gfm`  GitHub-Flavored Markdown baut direkt auf CommonMark auf
- {doc}`demo`  CommonMark-Syntax in der Praxis erleben
:::

---

## **Quellen & Weiterführende Literatur**

| **Ressource** | **Beschreibung** | **Link** |
|-----------|--------------|------|
| CommonMark Spec | Offizielle Spezifikation v0.31.2 | [commonmark.org](https://commonmark.org) |
| CommonMark Tutorial | Interaktives Lernen | [commonmark.org/help/tutorial](https://commonmark.org/help/tutorial/) |
| Babelmark | Vergleich von Implementierungen | [babelmark.github.io](https://babelmark.github.io) |
| Wikipedia: Markdown | Geschichte und Überblick | [en.wikipedia.org/wiki/Markdown](https://en.wikipedia.org/wiki/Markdown) |
| History of Markdown | Detaillierte Geschichte | [hackmd.io](https://hackmd.io/blog/2026/02/11/markdown-history) |
| Daring Fireball | Originale Markdown-Beschreibung | [daringfireball.net](https://daringfireball.net/projects/markdown/) |
