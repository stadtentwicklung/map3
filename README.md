# :world_map: Höhenmodell & Volllaufmodell
:white_check_mark: Höhenunterschiede eines Planungsbereiches verdeutlichen (Überhöhung) und als 3D-Szene im Web publizieren mit QGIS und Open-Source-Data.

## :computer: Link [https://stadtentwicklung.github.io/map3/)

### :camera_flash: Screenshot:
![Screenshot der GitHub-Pages App](https://raw.githubusercontent.com/stadtentwicklung/map3/master/img/screenshot.JPG)

## :rocket: Workflow

### :computer: Internet, QGIS und GitHub - mehr ist nicht nötig

Für ein kleines Gebiet in Cottbus (kleiner 1km²) wurde eine vereinfachte Geländehöhenanalyse durchgeführt. Das Areal ist insgesamt sehr flach mit 5m Höhenunterschied. Herausfinden lässt sich dass über eine Analyse in QGIS von z.B. Vermessungspunkten. Diese xyz-Dateien lassen sich für das Bundesland Brandenburg kostenfrei herunterladen über den [Geobroker der Landesvermessung](https://geobroker.geobasis-bb.de/basiskarte.php?mode=startup&aProductId=488a2b53-564f-43eb-88ec-0d87bb43ed20). Das Projekt 3D-Höhenmodell benötigt diese Datei nicht. Erforderlich ist eine Schummerung, bei der eine künstliche Lichtquelle auf die Geländehöhen geworfen wird, um im Ergebnis die Oberflächenform des Geländes gut zu veranschaulichen. Dann benötigt es nur noch ein Orthofoto, um die Orientierung zu vereinfachen. Die Schummerung wird als GeoTIFF vom [Geobroker der Landesvermessung](https://geobroker.geobasis-bb.de/basiskarte.php?mode=startup&aProductId=488a2b53-564f-43eb-88ec-0d87bb43ed20) bereitgestellt. Das Orthofoto wird erzeugt aus einem Orthofoto-WMS der Landesvermessung. 

...

![Screenshot Workflow](https://raw.githubusercontent.com/stadtentwicklung/map3/master/img/qgis.JPG)

Nach dem Speichern der Tiles als Webmap-Paket, wurde der HTML-, CSS- und JavaScript-Code individuell verfeinert z.B. mit der Funktion Standortermittlung. Alle Veränderungen lassen sich lokal über den Browser beurteilen. Das überarbeitete Paket ist in dieses Repository auf GitHub über die Kommandozeile hineingeladen (das Projekt besteht auf Grund der Tiles aus fast 500 Dateien, welche nicht mit Drag & Drop platziert werden können). Die aktivierte Funktion [GitHub-Pages](https://pages.github.com/) erlaubt jetzt, die Karte online über eine [Domain](https://stadtentwicklung.github.io/map3/) aufzurufen.

### :coffee::coffee::coffee: by [Stefan](https://github.com/stefanstoehr)
