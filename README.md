## Dokumentation fuer die Einrichtung der notwendigen Komponenten fuer Ediarum (Setup-Doku)

Diese Doku ist in DITA-XML geschrieben.

### Einstiegspunkt

Wir definieren die Inhaltsstruktur (und das Glossar?) in der DITA bookmap [`setup-doc_DE.ditamap`](setup-doc_DE.ditamap).

### Build-Targets

#### Version

Bei jeder Ver?ffentlichung ist die Version einzutragen unter /static/footer.xml
Z.B.: Version 0.1. Stand: 26.10.2018
Ausserdem die Versionsangaben f?r die abgedeckte Software (eXist, Oxygen) und f?r die abgedeckten ediarum-Komponenten.

#### Oxygen Webhelp-responsive

##### Konfiguration

Die Oxygen-Projektdatei [`setup-doc_DE.xpr`](../setup-doc_DE.xpr) enthaelt eine Konfiguration fuer DITA-OT Transformation in ein *Webhelp-responsive* target.
Darin sind ein paar erforderliche Variablen gesetzt:

| Variable | Wert |
|----------|------|
| `args.copycss` | `yes` |
| `args.css` | `${pd}/custom.css` |
| `webhelp.fragment.footer` | `${pd}/develop/static/footer.xml` |
| `webhelp.logo.image` | `${pd}/ediarum_basis/bbaw_logo.png` |

Desweiteren wurden Variablen gesetzt, um die Short Descriptions anzuzeigen, Navigationselemente anzuzeigen und aehnliches, ueber das "Configure Transformation Scenarios"-Fenster (siehe https://www.oxygenxml.com/doc/versions/21.1/ug-editor/topics/wh-responsive-output.html). Diese sind ebenfalls in ediarum_doku.xpr gespeichert.

Weitere Infos, wie man den Output konfiguriert: https://www.oxygenxml.com/doc/versions/21.1/ug-editor/topics/wh-responsive-output.html

Projektspezifisches CSS: commmon/custom.css

##### Ausfuehrung

Um die Transformation aus dem Oxygen heraus auszufuehren, waehlt man die DITA map (`setup-doc_DE.ditamap`) im *Project Manager* aus, macht Rechtsklick und geht im Kontextmenu zu *Transform > Apply Transformation Scenario*.
Beim ersten Durchlauf ist darauf zu achten, dasz unter *Transform > Configure Transformation Scenario(s)* als anzuwendendes Transformationsszenario tatsaechlich das in der Projektdatei definierte ausgewaehlt ist (das blaue ganz unten, "Ediarum Setup Doku DE") und nicht eines der Standard-Scenarien von Oxygen (die gelben oben).

Wenn der Build erfolgreich verlaeuft, sollte die HTML-Datei fuer die landing page unter `/out/webhelp-responsive/index.html` sein.


#### Deployment

Wir ver?ffentlichen die HTML-Webhelp-Builds auf [`ediarum.org/docs`](http://ediarum.org/docs).

Vorgehen:
Auf dem Server telotawebpublic das Verzeichnis mit dem HTML-Output kopieren nach: /var/www/html/ediarum-org/�� (z.B. mithilfe des Midnight Commander)

### Editorvariablen


<!--- vim: set ts=2 sw=2 tw=100 noet ft=markdown : -->
