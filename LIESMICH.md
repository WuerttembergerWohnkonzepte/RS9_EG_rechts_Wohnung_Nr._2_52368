# Roseggerstrasse 9, Kirchheim unter Teck, Wohnung Nr. 2 (EG rechts)

## Was in diesem Ordner liegt

    index.html          das Expose
    bilder/             14 Bilddateien, vom Expose eingebunden
    unterlagen/         18 PDF, ueber die Downloadkarten verlinkt

Alle drei muessen beieinander bleiben. Fehlt "bilder", zeigt die Seite
keine Fotos. Fehlt "unterlagen", laufen die Downloads ins Leere.

Zusaetzlich liegt eine Stufe hoeher die Datei
`Vorschau_Roseggerstrasse-9_Wohnung-2.html`. Darin sind alle Bilder
eingebettet, sie laesst sich also per Doppelklick oeffnen und
weitergeben. Die Downloadkarten funktionieren dort nicht, weil der
Ordner "unterlagen" fehlt. Die Vorschau ist nur zum Gegenlesen,
veroeffentlicht wird der Ordner.

## Zahlengrundlage im Expose

Alle Werte stammen aus EG_rechts.xlsx.

    Kaufpreis                    192.000 EUR
    Kaufpreis je m2                3.231 EUR
    Erwerbsnebenkosten 7 %        13.440 EUR
    Gesamtinvestition            205.440 EUR
    Grund und Boden               35.567 EUR
    Abschreibungsbasis           169.873 EUR   = 82,69 % der Gesamtinvestition
    Restnutzungsdauer            19 Jahre      Gutachten WE2 vom 08.06.2026
    Abschreibung im Jahr           8.941 EUR   = 5,26 %
    Nettokaltmiete                   504 EUR   = 8,48 EUR/m2
    Mietsubvention                 5.190 EUR   siehe Staffelung unten
    Cashflow nach Steuern, 1. Monat   23,18 EUR bei Vollfinanzierung

Die Mietsubvention ist mit **5.190 EUR** angesetzt, wie in Zelle M44 der
Kalkulation. Damit geht auch die Herleitung des Kaufpreises auf:
185.000 + 5.190 + 1.810 Aufrundung = 192.000 EUR.

Die Staffelung folgt den Kalenderjahren, wobei 2026 nur der Dezember
zaehlt:

    Dezember 2026       150 EUR                 150 EUR
    2027 bis 2029       100 EUR je Monat      3.600 EUR
    2030 bis 2032        40 EUR je Monat      1.440 EUR
    Summe                                     5.190 EUR

Genau so rechnet auch die Zelle M44 der Kalkulation.

Im Rechenmodell der index.html steht dafuer

    sub:[100, 100, 100, 40, 40, 40, 0, 0, 0, 0]

Das sind die Monatsbetraege fuer die Jahre 1 bis 10 nach dem Kauf, also
2027 bis 2036. Die 150 EUR fuer den Dezember 2026 liegen davor und sind
im Rechner nicht enthalten, weil er in ganzen Jahren ab dem Kauf rechnet.
Auf die Zehnjahressumme wirken sie mit 150 EUR, das sind 1,25 EUR im
Monat.

## Noch ein Unterschied zur Kalkulation

Der Rechner im Expose setzt die erste Mieterhoehung erst nach drei
Jahren an, die Kalkulation dagegen schon 2027, also im ersten
Projektionsjahr. Das Expose rechnet damit vorsichtiger als die
Kalkulation. Wenn es angeglichen werden soll, ist im Rechenmodell die
Zeile

    var stufen=Math.floor((j-1)/3);

auf

    var stufen=Math.floor(j/3)+1;

zu aendern. Dann steigen alle ausgewiesenen Ergebnisse.

## Vor der Veroeffentlichung erledigen

1. **Adresse der veroeffentlichten Seite eintragen.** In der index.html
   steht im Kapitel Finanzierung genau eine Zeile:

       var EXPOSE_URL = "";

   Dort die Adresse der GitHub-Pages-Seite eintragen. Bleibt das Feld
   leer, steht in der vorbereiteten Mail an die Moeglichmacher ein
   Platzhalter statt des Links.

2. **Herleitung der Kaufpreisaufteilung vervollstaendigen.** Die
   uebergebene Datei enthaelt noch Platzhalter: "Erdgeschoss [bitte
   ergaenzen: links oder rechts]" ist rechts, der Kaufpreis fehlt, der
   Gebaeudeanteil und die Prozentwerte sind offen, und der Absatz zur
   Vermietungssituation ist leer. Fuer den letzten Punkt: Nettokaltmiete
   504 EUR, Mietverhaeltnis seit 15.09.2011, Miete unter der ortsueblichen
   Vergleichsmiete, dadurch eingeschraenkte Nutzbarkeit.

3. **Entfernungen im Kapitel Lage pruefen.** Die Gehzeiten und
   Fahrzeiten sind aus dem Expose der Wohnung Nr. 1 uebernommen und
   gerundet. Bitte einmal gegenlesen.

4. **Kostenrahmen Modernisierung.** Im Kapitel 07 steht bewusst kein
   Kostenrahmen, weil fuer dieses Haus kein Handwerkerangebot vorliegt.
   Sobald es da ist, laesst es sich in den rechten Kasten einsetzen, so
   wie es im Expose Tulpenstrasse 15 aufgebaut war.

5. **Fotos vom Treppenhaus und vom Keller.** Sie fehlen noch und liessen
   sich in die Galerie in Kapitel 02 ergaenzen.

## Zu den Bildern

Die sieben Innenaufnahmen zeigen die Wohnung Nr. 2 selbst, also den
heutigen bewohnten Bestandszustand. Sie stehen deshalb in Kapitel 02 und
nicht im Modernisierungskapitel. In einer Galerie liegen sie zusammen mit
der Aufnahme des Gemeinschaftsgartens, der unbearbeitet ist.

Die Strassenansicht ist nur das Titelbild und steht nicht in der Galerie.

Der Hinweis auf die KI-Aufbereitung steht kurz unter der Galerie und
ausfuehrlich in den rechtlichen Hinweisen unter "Einsatz von KI".

Der Grundriss ist ein Ausschnitt aus dem Aufteilungsplan, Seite
Erdgeschoss, Planstand 08.06.2026. Er zeigt nur die Wohnung Nr. 2 mit
allen Raumgroessen. Der vollstaendige Plan liegt in den Unterlagen.

## Hochladen

Ein eigenes Repository fuer diese Wohnung anlegen. Dann auf
"Add file", danach "Upload files", und in das Fenster alles drei
zusammen ziehen:

    index.html
    bilder            (der ganze Ordner)
    unterlagen        (der ganze Ordner)

Wichtig: nicht den Ordner "Roseggerstrasse-9-EG-rechts" hochladen,
sondern seinen Inhalt. Die index.html muss im Repository ganz oben
liegen.

## Pages einschalten

Settings, dann Pages. Bei Source "Deploy from a branch" waehlen,
Branch `main`, Ordner `/ (root)`. Speichern. Der erste Aufbau dauert
ein bis zwei Minuten.

## Groessen

Keine Datei ist groesser als rund 4,7 MB, der Weblader von GitHub nimmt
einzelne Dateien bis 25 MB. Die Scans wurden auf 150 dpi gerechnet, aus
45 MB wurden 19 MB. Die Seite selbst laedt beim Besucher mit rund
1,7 MB, davon 1,6 MB Bilder. Das Paket "Alle herunterladen" ist rund
19 MB gross, das dauert auf dem Telefon einen Moment.

## Nicht enthalten, mit Absicht

Nicht im Ordner "unterlagen" liegen Grundbuchauszug,
Restnutzungsdauergutachten, Herleitung der Kaufpreisaufteilung und die
Mietvertraege. Sie enthalten personenbezogene Daten. Auf GitHub Pages
ist jede Datei im Repository oeffentlich abrufbar, auch wenn sie auf der
Seite nicht verlinkt ist. Im Expose steht deshalb, dass diese Unterlagen
bei ernsthaftem Kaufinteresse nachgereicht werden.

Ebenfalls nicht enthalten sind das Expose und die
Modernisierungsaufstellung der Wohnung Nr. 1, das sind Verkaufsunterlagen
einer anderen Einheit.

Ein Hinweis zur Teilungserklaerung, die im Ordner liegt: Sie enthaelt in
Abteilung III die Grundschulden des Verkaeufers. Das war in Sindelfingen
genauso, deshalb liegt sie hier wieder im oeffentlichen Ordner. Falls das
nicht gewuenscht ist, die Datei `01_Teilungserklaerung.pdf` loeschen und
den ersten Eintrag in der Liste `DOKS` in der index.html entfernen.

## Falls ein Ordner anders heissen soll

In der index.html steht im Skript genau eine Zeile:

    var DOKBASE='unterlagen/';

Nur diese aendern. Der Schraegstrich am Ende muss bleiben.
Der Bildordner ist in den Bildpfaden hinterlegt und heisst "bilder".

## Hinweis zum Oeffnen von der Festplatte

Oeffnest du die index.html per Doppelklick, sperrt der Browser bei
manchen Einstellungen den Zugriff auf Nachbarordner. Die Seite
erscheint, die Downloads funktionieren dort aber nicht immer. Auf der
veroeffentlichten Seite laeuft alles.
