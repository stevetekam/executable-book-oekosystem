# **GitHub-Flavored Markdown (GFM)**

:::{note}
**CommonMark + praktische Erweiterungen für Entwickler**

GFM ist eine strikte Obermenge von CommonMark. Alles was in CommonMark
funktioniert, funktioniert auch in GFM plus mächtige Erweiterungen,
die GFM zum meistgenutzten Markdown-Dialekt der Welt gemacht haben.
:::

---

## **1. Was ist GFM?**

GitHub-Flavored Markdown (GFM) ist der Markdown-Dialekt von GitHub.
Er wird täglich von Millionen Entwicklern verwendet in README-Dateien,
Issues, Pull Requests, Wikis und Kommentaren.

Die formelle GFM-Spezifikation wurde **2017** veröffentlicht und ist
heute unter [github.github.com/gfm](https://github.github.com/gfm/)
abrufbar.

GFM wird nicht nur auf GitHub verwendet, sondern auch auf:

| **Plattform** | **GFM-Unterstützung** |
|-----------|-------------------|
| GitHub | ✅ Nativ |
| GitLab | ✅ Weitgehend kompatibel |
| Stack Overflow | ✅ Teilweise |
| Discord | ✅ Teilweise |
| Reddit | ✅ Teilweise |
| Jupyter Notebooks | ✅ CommonMark-Basis |

---

## **2. GFM = CommonMark + Erweiterungen**

:::{tip}
**Offizielle Ressourcen**
- GFM Spezifikation: [github.github.com/gfm](https://github.github.com/gfm/)
- GitHub Doku: [docs.github.com/en/get-started/writing-on-github](https://docs.github.com/en/get-started/writing-on-github)
:::

---

## **3. Tabellen**

Tabellen sind eine der nützlichsten GFM-Erweiterungen.
Sie werden mit Pipe-Symbolen `|` und Bindestrichen `-` erstellt.

### **Syntax**

````markdown
| **Spalte 1** | **Spalte 2** | **Spalte 3** |
|----------|----------|----------|
| Wert A   | Wert B   | Wert C   |
| Wert D   | Wert E   | Wert F   |
````

### **Ausrichtung**

````markdown
| **Links**      | **Zentriert**  | **Rechts**     |
|:-----------|:----------:|----------:|
| Text       | Text       | Text       |
| 1234       | 1234       | 1234       |
````

**Ergebnis:**

| **Links**      | **Zentriert**  | **Rechts**    |
|:-----------|:----------:|----------:|
| Text       | Text       | Text      |
| 1234       | 1234       | 1234      |

### **Praxisbeispiel**

| **Werkzeug**     | **Typ**            | **Basis**       | **Lizenz**  |
|--------------|----------------|-------------|---------|
| CommonMark   | Standard       | Markdown    | –       |
| GFM          | Dialekt        | CommonMark  | –       |
| MyST         | Erweiterung    | CommonMark  | MIT     |
| Jupyter Book | Publisher      | MyST        | BSD     |
| Sphinx       | Build-Tool     | reST / MyST | BSD     |

---

## **4. Task-Listen**

Task-Listen ermöglichen interaktive Checklisten direkt im Markdown.

### **Syntax**

````markdown
- [x] CommonMark verstehen
- [x] GFM kennenlernen
- [ ] Eigenes Jupyter Book erstellen
- [ ] Inhalte publizieren
````

**Ergebnis:**

- [x] CommonMark verstehen
- [x] GFM kennenlernen
- [ ] Eigenes Jupyter Book erstellen
- [ ] Inhalte publizieren

:::{tip}
Auf GitHub erscheinen Task-Listen in Issues als Fortschrittsbalken –
ein praktisches Werkzeug für Projektmanagement direkt im Repository.
:::

---

## **5. Strikethrough: Durchstreichen**

Durchgestrichener Text signalisiert veraltete oder entfernte Inhalte.

### **Syntax**

````markdown
~~veraltete Information~~ aktuelle Information
~~Diese Funktion ist durchgestrichen~~
````

Ergebnis:

~~veraltete Information~~ aktuelle Information

~~Diese Funktion ist durchgestrichen~~

---

## **6. Autolinks**

GFM erkennt URLs automatisch und macht sie klickbar –
ohne eckige Klammern oder Markdown-Link-Syntax.

### **Syntax**

````markdown
Besuche https://commonmark.org für die offizielle Spezifikation.
Oder schreibe an kontakt@beispiel.de
````

**Ergebnis:** URLs werden automatisch als Links dargestellt.

---

## **7. Fenced Code Blocks mit Syntax-Highlighting**

GFM erweitert CommonMark's Codeblöcke um
**automatisches Syntax-Highlighting** für hunderte Programmiersprachen.

### **Syntax**

````markdown
```python
import pandas as pd

df = pd.read_csv("daten.csv")
print(df.head())
```
````

````markdown
```bash
jb build .
sudo apt update && sudo apt upgrade
```
````

````markdown
```yaml
title: Mein Jupyter Book
author: Max Mustermann
execute:
  execute_notebooks: "off"
```
````

---

## **8. CommonMark vs. GFM: Vollständiger Vergleich**

| **Feature** | **CommonMark** | **GFM** |
|---------|-----------|-----|
| Überschriften | ✅ | ✅ |
| Fett / Kursiv | ✅ | ✅ |
| Listen | ✅ | ✅ |
| Links & Bilder | ✅ | ✅ |
| Codeblöcke | ✅ | ✅ |
| Blockzitate | ✅ | ✅ |
| Horizontale Linie | ✅ | ✅ |
| **Tabellen** | ❌ | ✅ |
| **Task-Listen** | ❌ | ✅ |
| **Strikethrough** | ❌ | ✅ |
| **Autolinks** | ❌ | ✅ |
| **Syntax-Highlighting** | ❌ | ✅ |

---

## **9. GFM und das Executable Book Ökosystem**

GFM ist nicht nur ein GitHub-Werkzeug, es ist der gemeinsame Nenner
des gesamten Executable Book Ökosystems:

- **Jupyter Notebooks** verwenden CommonMark/GFM in Markdown-Zellen
- **MyST Markdown** baut auf CommonMark auf und fügt wissenschaftliche
  Erweiterungen hinzu
- **Jupyter Book** akzeptiert GFM-kompatible Markdown-Dateien nativ
- **Sphinx** verarbeitet GFM über den MyST-Parser

:::{important}
Wer GFM beherrscht, hat die Grundlage für das gesamte
Executable Book Ökosystem und für nahezu jede moderne
Dokumentations- und Publikationsplattform.
:::

---

## **Verbindung zu anderen Kapiteln**

:::{important}
**Navigation im Buch**

- {doc}`commonmark`  Die Basis, auf der GFM aufbaut
- {doc}`demo`  GFM-Syntax live in der Praxis erleben
:::

---

## **Quellen & Weiterführende Literatur**

| **Ressource** | **Beschreibung** | **Link** |
|-----------|--------------|------|
| GFM Spezifikation | Offizielle Spezifikation | [github.github.com/gfm](https://github.github.com/gfm/) |
| GitHub Doku | Schreiben auf GitHub | [docs.github.com](https://docs.github.com/en/get-started/writing-on-github) |
| CommonMark Spec | Die Basis von GFM | [commonmark.org](https://commonmark.org) |
| Wikipedia: Markdown | Geschichte & Überblick | [en.wikipedia.org/wiki/Markdown](https://en.wikipedia.org/wiki/Markdown) |
| History of Markdown | Von 2004 bis heute | [web2md.org](https://web2md.org/blog/history-of-markdown) |
| mdkit.io: GFM | GFM erklärt | [mdkit.io](https://mdkit.io/blog/github-flavored-markdown) |
