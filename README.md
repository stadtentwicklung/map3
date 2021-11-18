# :world_map: Interaktives online 3D-Höhenmodell mit Volllauffunktion
:white_check_mark: Höhenunterschiede eines Planungsbereiches verdeutlichen (Überhöhung) und als 3D-Szene im Web publizieren mit QGIS und Open-Source-Data.

## :computer: Link https://stadtentwicklung.github.io/map3/

### :camera_flash: Screenshot:
![Screenshot der GitHub-Pages App](https://raw.githubusercontent.com/stadtentwicklung/map3/master/img/screenshot.JPG)

## :rocket: Workflow

### :computer: Internet, QGIS und GitHub - mehr ist nicht nötig

Für ein 1km² großes Gebiet in CB wurde eine vereinfachte Geländehöhenanalyse durchgeführt. Das Areal ist flach mit max. 5m Höhenunterschied, was eine Analyse in QGIS von Vermessungspunkten ergab. Diese xyz-Dateien lassen sich für das Bundesland Brandenburg kostenfrei herunterladen über den [Geobroker der Landesvermessung](https://geobroker.geobasis-bb.de/basiskarte.php?mode=startup&aProductId=488a2b53-564f-43eb-88ec-0d87bb43ed20) im lokal üblichen Koordinatenbezugssystem EPSG:25833. Die Höheninformationen sind ersichtlich über: Rechtsklick auf Layer Vermessungspunkte -> Eigenschaften -> Symbolisierung -> Pull-Down: Abgestuft -> Pull-Down: Spalte mit Höhenwerten wählen -> Klassifizieren anklicken (ziehmlich weit unten). Dargestellt ist jetzt eine stufenweise Differenzierung vom kleinsten zum größten Höhenwert. Die Parameter der Symbolisierung lassen sich weiter verfeinern (Farben, Farberlauf, Ausdehnung der Abstufung).

Das interaktive online Projekt 3D-Höhenmodell benötigt diese Datei jedoch nicht. Die xyz-Daten bilden jedoch das Hauptlayout, in dem ein vereinfachtes Höhestufennmodell mit QGIS dargestellt ist.
![Screenshot der PDF mit Höhenstufenmodell und Link zum interaktiven Höhenmodell](https://raw.githubusercontent.com/stadtentwicklung/map3/master/img/stufen.jpg)
Das interaktive Szenario ist sozusagen **on top** - der beistehende Link (oben rechts im Bild) zu einem online 3D-Höhenmodell _upgraded_ das sonst so _gewöhnliche_ PDF. Es bildet ein zusätzliches Analyseerlebnis. 

Für die Erstellung des 3D-Szenarios benötigt QGIS nur zwei Informationen: (1) Eine Schummerung, bei der eine künstliche Lichtquelle auf die Geländehöhen geworfen wird, um im Ergebnis die Oberflächenform des Geländes gut zu veranschaulichen. (2) Ein Orthofoto, um die Orientierung auf dem Mesh zu vereinfachen. Die Schummerung wird als GeoTIFF vom [Geobroker der Landesvermessung](https://geobroker.geobasis-bb.de/basiskarte.php?mode=startup&aProductId=488a2b53-564f-43eb-88ec-0d87bb43ed20) kostenfrei bereitgestellt. Das Orthofoto wird erzeugt aus einem ebenfalls kostenfreiem Orthofoto-WMS der [Landesvermessung](https://geobroker.geobasis-bb.de/gbss.php?MODE=GetProductInformation&PRODUCTID=253b7d3d-6b42-47dc-b127-682de078b7ae). Erzeuge zuerst aus dem WMS ein einzelnes GeoTIFF: Rechtsklick auf dem WMS-Layer -> Exportieren -> Speichern als... -> Drop-Down: GeoTIFF -> Ausdehnung: Aus Layer berechnen _Schummerung_ -> OK. Damit existiert jetzt ein separates Orthofoto in gleicher Abmessung wie die Schummerung. Der WMS-Layer kann gelöscht werden. Der Layer mit dem neuen Orthofoto muss über dem Layer mit der Schummerung liegen. Die Erstellung des 3D-Szenarios erfolgt mit dem Plugin [qgis2threejs](https://github.com/minorua/Qgis2threejs), dass eventuell über das Menü _Erweiterungen_ importiert werden muss, falls du es zum erstenmal benutzt. Im Menü _Web_ ist es dann aufrufbar. Bei _Scene Settings_ ist standardmäßig eine Überhöhung (Vertical exaggregation) von 1.0 eingestellt. Nach optischer Analyse sind das ca. 100m vertikale Überhöhung. Über File -> Export to Web wird das Projekt als HTML/Three.js-Paket gespeichert. Den Parameter **Enable the Viewer to Run locally** aktivieren, um die gespeicherte index.html-Datei nach dem       

...

![Screenshot Workflow](https://raw.githubusercontent.com/stadtentwicklung/map3/master/img/qgis.JPG)

Nach dem Speichern der Tiles als Webmap-Paket, wurde der HTML-, CSS- und JavaScript-Code individuell verfeinert z.B. mit der Funktion Standortermittlung. Alle Veränderungen lassen sich lokal über den Browser beurteilen. Das überarbeitete Paket ist in dieses Repository auf GitHub über die Kommandozeile hineingeladen (das Projekt besteht auf Grund der Tiles aus fast 500 Dateien, welche nicht mit Drag & Drop platziert werden können). Die aktivierte Funktion [GitHub-Pages](https://pages.github.com/) erlaubt jetzt, die Karte online über eine [Domain](https://stadtentwicklung.github.io/map3/) aufzurufen.

### :coffee::coffee::coffee: by [Stefan](https://github.com/stefanstoehr)
