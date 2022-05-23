layout: true
  
<div class="my-header"></div>

<div class="my-footer">
  <table>
    <tr>
      <td style="text-align:right">Sächsische Landesbibliothek – Staats- und Universitätsbibliothek</td>
      <td>2. Juni 2022</td>
      <td style="text-align:right"><a href="https://www.slub-dresden.de/">www.slub-dresden.de</a></td>
    </tr>
    <tr>
      <td style="text-align:right">Referate 4.3, 2.5</td>
      <td />
    </tr>
  </table>
</div>

<div class="my-title-footer">
  <table>
    <tr>
      <td style="text-align:left"><b>Kay-Michael Würzner</b></td>
      <td style="text-align:left"><b>Robert Sachunsky</b></td>
      <td style="text-align:left"><b>Alexander Lasch</b></td>
    </tr>
    <tr>
      <td style="text-align:left">Referat 4.3</td>
      <td style="text-align:left">Referat 2.5</td>
      <td style="text-align:left">TU Dresden</td>
    </tr>
    <tr>
      <td style="font-size:8pt"><b>2. Juni 2022</b></td>
    </tr>
    <tr>
      <td style="font-size:8pt">8. Bibliothekskongress Leipzig 2022</td>
    </tr>
  </table>
</div>

---

class: title-slide
count: false

# Verbesserung automatischer Handschrifterkennung durch bürgerwissenschaftliche Transkription

---

# Überblick

- Prinzipien der Handschriftenerkennung
  + Datengetriebene Erkennungsmodelle
  + Vergleich mit Texterkennung von Drucken
  + Anforderungen an Trainingsdaten
- Beteiligungskulturen
  + Motivation und Motive
  + Szenarien der Einbindung externer Kompetenzen
- **Diskussion:** wissenschaftliche Bibliotheken und bürgerwissenschaftliche Beteiligung

---

class: part-slide
count: false

# Prinzipien der Handschriftenerkennung

---

## Wie funktioniert's?

- Ziel: Transformation von Bilddaten in maschinenlesbaren Volltext
    + schrittweise Verarbeitung

<center>
<img src="img/nbg_region.png" width="400px" />
</center>
<center>
<p>↓</p>
</center>
<center>
<p style="display: inline-block; text-align: left; font-size: 16pt.; font-style: italic;">
oberwähntem Tage mancher sorgliche Gedanke auf,<br/>
&amp; wir seufzten öfters zum Heiland, daß Er uns<br/>
vor allem Schaden, der uns etwa in der folgen-<br/>
den Nacht begegnen könnte, in Gnaden bewahren
</p>
</center>

---

## Wie funktioniert's?

- Schritt 1: Zeilenerkennung
    + **regelbasierte** (Bildmorphologie) oder
    + **datengetriebene** Verfahren (e.g. Pixelklassifikation)

<center>
<img src="img/nbg_region.png" width="400px" />
</center>
<center>
<p>↓</p>
</center>
<center>
<img src="img/nbg_lines.png" width="400px" />
</center>

---

## Wie funktioniert's?

- Schritt 2: Vektorisierung
    + **Skalierung** auf einheitliche Höhe
    + **Unterteilung** in 1 Pixel breite Streifen

<center>
<img src="img/nbg_lines.png" width="400px" />
</center>
<center>
<p>↓</p>
</center>
<center>
<img src="img/nbg_grid.png" width="400px" />
</center>

---

## Wie funktioniert's?

- Schritt 3: Zeichenerkennung
    + **Übergangswahrscheinlichkeiten** zwischen Vektoren
    + Rückgriff auf (vorab) trainiertes **Modell**

<center>
<img src="img/nbg_grid.png" width="400px" />
</center>
<center>
<p>↓</p>
</center>
<center>
<p style="display: inline-block; text-align: left; font-size: 16pt.; font-style: italic;">
oberwähntem Tage mancher sorgliche Gedanke auf,<br/>
&amp; wir seufzten öfters zum Heiland, daß Er uns<br/>
vor allem Schaden, der uns etwa in der folgen-<br/>
den Nacht begegnen könnte, in Gnaden bewahren
</p>
</center>

---

## Datengetriebene Erkennungsmodelle

<center>
<img src="img/nbg_grid.png" width="400px" />
</center>

.cols[
.sixty[
- Tabellen mit fester Anzahl Zeilen und variabler Anzahl Spalten
- Pixelspalten als Vektorfolge
  + charakteristische Abfolge pro Zeichen (und Wort)
+ **Übergangswahrscheinlichkeiten** zwischen Vektoren = trainierbares Modell
]
.fourty[
<center>
<img src="img/detail_mask.png" width="190px" />
</center>
<center>
<p>↓</p>
</center>
<center>
<img src="img/pixel_cols.png" width="190px" />
</center>
]
]

---

## Vergleich mit Texterkennung von Drucken

- einheitliches Paradigma für Erkennung von Handschrift und Druck (und Noten etc.)
  + Training: auf Zeilenebene zugeordnete Bild-Text-Paare
- jedoch höhere Varianz bei Handschriften
  + Gestalt (Hand vs. Schriftart)
  + Materialität (Stift, Feder, Papier, Presse)
  + Aufwand (Notiz, Brief, Zeitung, Festschrift ...)

---

## Anforderungen an Trainingsdaten

- Quantität
  + größere Menge an Trainingsdaten (intra-individuelle Varianz)
  + schlechtere Übertragbarkeit trainierter Modelle (inter-individuelle Varianz)
- Qualität
  + (teilweise) schwerer zu lesendes Ausgangsmaterial
  + komplexere Aufbereitung für Training durch aufwendigere Segmentierung

ANIMATION

---

class: part-slide
count: false

# Beteiligungskulturen

---

## Motivation

- benötigte softwaretechnische Umgebung: **frei verfügbar**
- manuelle Aufwände (und Kosten) i.A. nicht abbildbar
- Unterstützung bei Erstellung von Trainingsdaten durch Freiwillige

<center>
<img src="img/components.svg" width="350px" />
</center>

---

class: part-slide
count: false

## Szenarien der Einbindung externer Kompetenzen

<!-- Workflow-Aspekte -->

- Arbeitsteilung
- Sichtbarkeit und Interesse
- Beitrag durch Freiwillige
- technische Unterstützung bei manueller Arbeit
- technische Unterstützung durch automatische Schritte

<!-- ff. am konkreten Beispiel: -->

---

### Soldatenbriefe

---

### Exkurs: Herrnhut Digital

---

### Nachrichten aus der Brüdergemeine: digit. Ed.

---

### Nachrichten aus der Brüdergemeine: Podcast

<center>
<img src="img/Herrnhut-Podcasts.png" width="950px" />
</center>

---

## Schlussfolgerungen

- Zielkonflikt:
  + Domänenexpertise (Kurrent, Hintergrundwissen) vs.
  + informationstechnische Fertigkeiten

  Vermeidung durch Etablierung geteilter Arbeitsabläufe
- Reduktion des manuellen Aufwands:
  + Transkription _ohne_ manuelle Segmentierung
  + Überbrückung durch OLR und automatische Alignierung von OCR und Transkription

<!-- Kompromiss zwischen Aufwand für weitestmögliche Automatisierung und Umfang der manuellen Nachbearbeitung -->

---

class: part-slide
count: false

# Wissenschaftliche Bibliotheken und bürgerwissenschaftliche Beteiligung

- auf allen Seiten…
  + Kompetenzen
  + Interesse
  + Wertschöpfung
- Bibliothek als…
  + Anbieter&Sammler von (Werk-)Daten
  + Vermittler (Zugang, Organisation, Wissen, Forschung)
  + technische Infrastruktur (Informationsdienste, Erschließung/Präsentation, Weiterentwicklung)

---

class: part-slide

# Danke für Ihre Aufmerksamkeit!

<center>
<a href="https://wrznr.github.io/bibliothekskongress-2022/">wrznr.github.io/bibliothekskongress-2022</a>
</center>
