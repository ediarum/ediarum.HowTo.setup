## Dokumentation für die Einrichtung der notwendigen Komponenten für Ediarum

### Einstiegspunkt

Wir definieren die Inhaltsstruktur (und das Glossar?) bis auf weiteres in der DITA bookmap [`setup.ditamap`](setup.ditamap).


### Build-Targets


#### Oxygen Webhelp-responsive

Die Oxygen-Projektdatei [`ediarum_doku.xpr`](../ediarum_doku.xpr) enthaelt eine Konfiguration fuer DITA-OT Transformation in ein *Webhelp-responsive* target.
Darin sind ein paar erforderliche Variablen gesetzt, die so oder so aehnlich aus [`ediarum_basis`](../ediarum_basis/) uebernommen wurden:

| Variable | Wert |
|----------|------|
| `args.copycss` | `yes` |
| `args.css` | `${pd}/custom.css` |
| `webhelp.fragment.footer` | `${pd}/develop/static/footer.xml` |
| `webhelp.logo.image` | `${pd}/ediarum_basis/bbaw_logo.png` |

Um die Transformation aus dem Oxygen heraus auszufuehren, waehlt man z.B. die DITA map (`setup.ditamap`) im *Project Manager* aus, macht Rechtsklick und geht im Kontextmenu zu *Transform > Apply Transformation Scenario*.

Wenn der Build erfolgreich verlaeuft, sollte die HTML-Datei fuer die landing page unter `develop/out/webhelp-responsive/index.html` sein.


##### Deployment

Fuer Review etc. stellen wir HTML-Webhelp-Builds auf [`telota.bbaw.de`](http://telota.bbaw.de/ediarum/manual/setup/) ins Internet.
Das Verzeichnis wo die Inhalte dazu hinkopiert werden muessen ist:

    root@telota.bbaw.de:/data1/projekte/ediarum/manual/setup


### Editorvariablen


