# Wörterwald – Laute hören & Wörter untersuchen

Ein statisches Lernspiel von **Förderfreude Games** für Klasse 1, Förderung und DaZ.
Die Kinder hören genau hin: Welcher Laut steht am Anfang, am Ende oder mitten im Wort? Es geht um **Laute, nicht um Buchstaben**.

Das Spiel besteht aus einer einzigen Datei (`index.html`). Es nutzt nur HTML, CSS und JavaScript, hat keine externen Ressourcen und setzt keine Cookies. Es nutzt weder Tracking noch lokalen Speicher.

## Stationen

| Nr. | Station | Aufgabe |
|---|---|---|
| 1 | Der Lauschbaum | Anlaut bestimmen |
| 2 | Das Waldecho | Endlaut bestimmen |
| 3 | Die Laut-Zwillinge | Zwei Bilder mit gleichem Anlaut finden |
| 4 | Das Echo-Paar | Zwei Bilder mit gleichem Endlaut finden (kein Reim) |
| 5 | Die Lautspur | Welches Wort enthält den Laut? |
| 6 | Der Lautpfad | Anfang, Mitte oder Ende? |
| 7 | Die große Wörterwald-Runde | Alle sechs Aufgabenarten gemischt |

Es gibt drei Stufen (leicht, mittel, schwer). Eine Runde endet nach 8 richtig gelösten Aufgaben, ohne Zeit, Punkte, Leben oder Game over. Ein Fehler gibt nur einen Hinweis, der die Lösung nicht verrät. Der Fortschritt wird als „Lauschpfad“ mit 8 Markierungen gezeigt.

## Bedienung

- Maus, Touch und Tastatur. Jede Ziehaufgabe (Lautpfad) lässt sich auch durch Antippen lösen.
- Sprachausgabe über die Sprachsynthese des Browsers (de-DE) mit sichtbaren Lautsprecher-Knöpfen. Ist keine deutsche Stimme vorhanden, werden die Knöpfe ausgeblendet. Die Aufgaben bleiben lösbar, denn die Wörter stehen sichtbar da. In der Stufe „schwer“ sind die Wörter bei verfügbarer Sprachausgabe zunächst verborgen („Wörter zeigen“).
- Reduzierte Bewegung (`prefers-reduced-motion`) wird beachtet.
- Die CSS-Variable `--badge` hält unten Platz frei, damit das Netlify-Badge keine Knöpfe verdeckt.

## Lautdaten

Jedes der 180 Wörter hat kuratierte Lautdaten: Laute mit Schreibung, Anlaut, Endlaut, Stationen und Ausschlussgründe. Anlaut und Endlaut kommen **nie** aus dem ersten oder letzten Buchstaben. Auslautverhärtung (Hund → /t/), sch, ch, pf, ng, ei, au und eu sind eigene Laute. Mehrdeutige Wörter sind für die betroffene Station ausgeschlossen.
Eine ausführliche Übersicht steht in `pruefung/materialuebersicht.html` (auch als CSV und PDF).
Jede Aufgabe wird beim Erzeugen automatisch geprüft: genau eine Lösung, keine doppelten Optionen, keine Buchstabenfallen bei den Ablenkern, genau ein Paar, genau eine Position.

## Dateien

```
index.html                   Das Spiel (Dateiname nicht ändern)
README.md
.gitignore
arbeitsblaetter/
  teilnehmeruebersicht.html / .pdf                 A4 quer, 30 Kinder × 10 Runden
  arbeitsblatt-1-laute-am-anfang-und-ende(.html/.pdf, -loesung)
  arbeitsblatt-2-wo-hoerst-du-den-laut(.html/.pdf, -loesung)
pruefung/
  materialuebersicht.html / .csv / .pdf            Lautdaten, Stationen, Fachprüfliste
```

Die Arbeitsblätter lassen sich ohne Ton lösen (A4 hoch, mit Lösungsblättern).

## Veröffentlichen (GitHub + Netlify)

1. Ordner in ein GitHub-Repository legen.
2. In Netlify „Add new site → Import from Git“ wählen. Kein Build-Befehl, Publish-Verzeichnis ist `/`.
3. `index.html` liegt im Hauptverzeichnis und wird direkt ausgeliefert.

## Hinweis zur Sprachausgabe

Die Qualität der Stimme hängt von Gerät und Browser ab. Einzelne Laute werden von der Sprachsynthese nicht rein gesprochen. Deshalb werden **ganze Wörter** vorgelesen, und die Laute entstehen durch das genaue Hinhören der Kinder. Die Lehrkraft kann die Wörter bei Bedarf selbst sprechen.
