# Drehbuchstruktur und Styling-Konfiguration für interaktive Lehrvideos

## 1. Drehbuch-Inhalt
### 1.1 Meta-Informationen:

- **Title**: Titel des Videos.
- **Author**: Name des Autors oder der Autoren.
- **Style**: Referenz zu einer Datei oder Konfiguration für das visuelle Design.

Um maximale Flexibilität zu gewährleisten und jedem Lehrenden die Möglichkeit zu geben, seinen eigenen Stil umzusetzen, habe ich in allen Beispielen das Attribut *style* integriert – ähnlich wie bei HTML in Verbindung mit CSS. Dieses Attribut erlaubt es, individuelle Anpassungen vorzunehmen. 

Falls das *style*-Attribut nicht explizit angegeben wird, greift ein voreingestellter Standardstil.

### 1.2 Szenen - Jede Szene repräsentiert einen Abschnitt des Videos:

Es wurde bei jedem Abschnitt ein spezifischer Typ (*slide*, *teleprompt*, *screencast*) festgelegt, um die Verarbeitung zu steuern. Der Typ gibt vor, wie der jeweilige Abschnitt weiterverarbeitet wird. 

Beispielsweise werden Abschnitte vom Typ *slide* in Bilder umgewandelt, die dann im Video angezeigt werden, während *teleprompt*-Abschnitte als Text für Sprecher genutzt werden können. Diese klare Zuordnung ermöglicht eine präzise und effiziente Weiterverarbeitung der Inhalte.

- **Slide**: Inhalte, die auf einer Folie dargestellt werden, einschließlich eines Titels und einer Liste oder Markdown-Formatierungen für den Text.
- **Teleprompt**: Der gesprochene Text für den Teleprompter, der die Inhalte der Szene beschreibt.
- **Quiz**: Fragen und mögliche Antworten für interaktive Elemente.
- **Screencast oder Video**: Verweis auf eine Datei oder Anweisung zur Aufnahme eines Screencasts.
- **Image/Graphic**: Beschreibung oder Referenz von Bildern/Grafiken.
- **Audio**: Verweis auf Audiodateien oder Hinweise für die Aufnahme von gesprochenem Text oder Hintergrundmusik.
 
<span style="color:red">Muss noch besprochen werden ob nötig:</span>

- **Actions**: Hinweise zu Kamerabewegungen, Effekten, Übergängen oder anderen visuellen Elementen.
- **Übergänge** : Beschreibung der Übergänge zwischen Szenen oder innerhalb einer Szene (fade-in, zoom, oder cut).

Jedes Element kann mehrfach in eine Szene eingefügt werden, die Reihenfolge im Drehbuch gibt darbei auch die Reihenfolge im Video an, Elemente wie Slide und die später aufgenommenen Videos durch den Telepromt überlagern sich natürlich

<br>

## 2. Drehbuch-Beispiele
In diesem Kapitel werden drei Drehbuch-Beispiele mit unterschiedlichen Strukturen vorgestellt. Ziel ist es, herauszufinden, welche Elemente und Aufteilungen am benutzerfreundlichsten sind. Darüber hinaus möchte ich zu jedem Beispiel kurz wichtige Erklärungen abgeben, weshalb diese Art und weise gewählt wurde.

### 2.1 eingerueckteVersion
Hier wird versucht den Aufbau ähnlich wie bei YAML zu halten, was eine klare Struktur gibt, da so immer auf anhieb erkannt werden kann welches Element dem andern Untergeordnet ist, 

### 2.2 markdownVersion
In diesem Beispiel wird ein Ansatz verwendet, der sich an der Markdown-Syntax orientiert. Alle bekannten Markdown-Befehle bleiben erhalten, sodass Überschriften (#, ##, ###, …) und Aufzählungen (-, +, *) wie gewohnt genutzt werden können. Dies ermöglicht eine einfache und intuitive Formatierung, insbesondere für Texte, die später auf Folien dargestellt werden.

Zusätzlich werden spezielle Markierungen eingeführt, um bestimmte Inhalte vom normalen Text abzugrenzen. Standardmäßig wird hierfür das „/“-Zeichen verwendet. Alternativ kann jedoch jedes andere Zeichen genutzt werden, solange es nicht bereits in der Markdown-Syntax vorkommt. Dieses System sorgt für eine flexible und leicht erweiterbare Struktur.

### 2.3 minimalistischeVersion
In diesem Ansatz wurde bewusst darauf geachtet, möglichst wenige zusätzliche Formatierungen wie Einrückungen oder spezielle Zeichen (#, -, etc.) aus Markdown zu verwenden. Ziel ist es, auch Nutzern ohne Vorkenntnisse in Markdown die Erstellung von Videos so einfach wie möglich zu machen.

Allerdings bringt dieser Ansatz einige Einschränkungen bei der Textformatierung mit sich. Beispielsweise ist es aktuell nicht vorgesehen, Fettdruck oder Kursivschrift in den Slides zu ermöglichen, da dies eine zusätzliche Syntax wie in Markdown oder LaTeX erfordern würde.

Die Verwendung von „---“ (drei Striche) dient dazu, die einzelnen Szenen optisch voneinander zu trennen und eine bessere Übersicht zu schaffen. Diese Markierungen werden jedoch später vom Interpreter oder Transpiler ignoriert und nicht verarbeitet.

<br>

## 3. Styledatei - Inhalt
Die Style-Datei, falls gewünscht oder erforderlich, ermöglicht die Anwendung unterschiedlicher Designs für verschiedene Studiengänge oder Lehrende. Dadurch können die Inhalte flexibel an die spezifischen Anforderungen und Vorlieben der Lehrenden angepasst werden, um den jeweiligen Gegebenheiten optimal zu entsprechen.


### 3.1 Slides

- **Titel**: Schriftgröße, Farbe, Position
- **Inhalt**: Schriftart, Absatzabstände, Farben
- **Hintergrund**: Einfarbig oder Bild
- **Effekte**: Animationen für Folienwechsel
- **Postion**: Gibt an wo das Element angezeigt wird

### 3.2 Teleprompter

- **Schriftart und Größe**: Lesbarkeit optimieren
- **Zeilenhöhe**: Für flüssiges Ablesen
- **Hervorhebungen**: Wichtige Wörter oder Phrasen farblich hervorheben

### 3.3 Quiz

- **Fragen**: Schriftgröße, Stil, Abstände
- **Antworten**: Unterscheidung zwischen richtigen und falschen Antworten (Farben Rot - Grün)
- **Postion**: Gibt an wo das Element angezeigt wird

### 3.4 Screencasts
- **Postion**: Gibt an wo das Element angezeigt wird

### 3.5 Bilder und Grafiken

- **Größe**: Maximale und minimale Dimensionen.
- **Positionierung**: Zentriert, links oder rechts.
- **Rahmen**: Farbe und Dicke des Rahmens.
- **Schatten**: Optional für visuelle Tiefe.
- **Postion**: Gibt an wo das Element angezeigt wird

### 3.6 Untertitel

- **Schriftart und Größe**: Gut lesbar, vorzugsweise ohne Serifen.
- **Hintergrund**: Halbtransparente Farbe für Kontrast.
- **Position**: Am unteren Rand des Bildschirms.
- **Postion**: Gibt an wo das Element angezeigt wird


<span style="color:red">Muss noch besprochen werden ob nötig:</span>

### 3.7 Übergänge (Transitions)

- **Effekte**: Typ (z. B. Fade, Slide, Zoom).
- **Dauer**: Zeit in Sekunden für Übergänge.
- **Weichheit**: Übergangskurve (linear, ease-in, ease-out).

### 3.8 Audio

- **Lautstärke**: Standard-Lautstärke für Hintergrundmusik, Effekte und Sprachaufnahmen.
- **Equalizer-Einstellungen**: Höhen, Mitten, Tiefen für Audio-Balancing.
- **Übergänge**: Fade-in, Fade-out für Musik oder Soundeffekte.

### 3.9 Animationen

- **Effekte**: Animationen für Texte, Bilder, Videos (z. B. Einblenden, Herauszoomen).
- **Geschwindigkeit**: Dauer und Intensität.
- **Trigger**: Wann Animationen gestartet werden (z. B. beim Laden, Klick).

<br>

Die Hauptidee der Style-Datei besteht darin, jedes Element, das im Drehbuch angelegt werden kann, auch individuell im Style-File konfigurieren zu können. Für allgemeine Einstellungen wie Schriftart, Farben oder grundlegende Layout-Eigenschaften soll es eine übergeordnete, allgemeine Konfiguration (eine Art "Parent") geben. Diese allgemeinen Einstellungen gelten standardmäßig für alle Elemente, können jedoch bei Bedarf von spezifischen Einstellungen auf der Ebene einzelner Elemente (den "Children") überschrieben werden.

Darüber hinaus sollte jedes Element flexibel ausgerichtet werden können, sodass der Benutzer die Position und Darstellung entsprechend seinen individuellen Anforderungen und Präferenzen anpassen kann.

<br>

## 4. Styledatei - Beispiele

Da die Syntax für das Drehbuch derzeit noch nicht final festgelegt ist, erscheint es wenig sinnvoll, bereits jetzt eine vollständig ausgearbeitete und exakt angepasste Struktur für die Style-Datei zu entwickeln. Um jedoch erste Ansätze zu testen und verschiedene Möglichkeiten zu erkunden, habe ich zwei Varianten vorbereitet – eine basierend auf JSON und eine auf CSS. Diese bieten eine solide Grundlage, um erste Einblicke in die Umsetzbarkeit und Flexibilität der Styles zu gewinnen.

### 4.1 JSON
Hiere habe ich eien Style Datei in JSON Format erstellt


### 4.2 CSS
Hiere habe ich eien Style Datei in CSS Format erstellt