# ATLAB-ABGABE-SANDRA
ATLAB Umgebungssteuerung für 2. Antritt
Use-Case Klientin Sandra: Jan Matousek

## Vorhandene Funktionen
Sandra kann beim linken Arm den Daumen und Zeigefinger bewegen sowie einfache Kopfbewegungen durchführen, außerdem kann sie ihre Sprache weiterhin verwenden.

## Umgesetzte Funktionen
.) Umgebungssteuerung über Sprachbefehle (Licht (Asterics Grid, openHAB, ACS), Jalousien (openHAB, ACS), Temperatur (ACS)
.) Internetradio (Asterics Grid)

## Verwendete Programme/Komponenten
Microsoft Spracherkennung, Asterics Runtime Environment (ARE), Asterics Configuration Suite (ACS), Asterics Grid und openHAB.
Die Steuerung von Licht Jalousien und dem Internetradio wird mit openHAB verknüpft (ARE ACS und localhost:8080)

### Spracherkennung (Microsoft) 
![Abbildung 1 Windows_Spracherkennung](workflows/Windows_Spracherkennung.png)
Da die Patientin motorisch beeinträchtigt ist wird der mit der Microsoft Spracherkennung verwendet um die Maus und Tastatur zu ersetzen. (Befehle Windows Spracherkennung: https://support.microsoft.com/de-de/windows/befehle-der-windows-spracherkennung-9d25ef36-994d-f367-a81a-a326160128c7) 

### AsTeRICs Grid
AsTeRICs Grid wird für die Umsetzung der Lichtsteuerung und das Aufrufen eines Internetradios für MusikverwendetFür die Umsetzung einer Umgebungssteuerung wird mittels openHAB ein zentraler Server verwendet der es erlaubt die Anwendungen ACS und ARE zu verbinden und in den Grid als auszuführende Aktion einzubinden. Durch das Einbinden eines ACS Modelles können AsTeRICs Aktionen durchgeführt und in openHAB visualisiert werden.
![Abbildung 2](workflows/GRD_Hauptgrid.png)
![Abbildung 3](workflows/GRD_Lichtsteuerung.png)
![Abbildung 4](workflows/GRD_AsTeRICS_Aktion.png)
![Abbildung 5](workflows/GRD_ACS_Einbindung.png)
![Abbildung 6](workflows/GRD_Webradio.png)
![Abbildung 7](workflows/GRD_Internetradio.png)

### openHAB ( open Home Automation Bus)
Mit openHAB werden AsTeRICs Programme verknüpft mit dem Ziel der vereinfachten Automatisierung im Smart Home Bereich oder in diesem Fall als barrierefreie Unterstützung für Menschen mit Beeinträchtigungen. OpenHAB dient auch als lokaler Server für die AsTeRICS Anwendungen und wird so gestartet:
![Abbildung 8](workflows/openHAB_start.png)
![Abbildung 9](workflows/openHAB_KitchenItem.png)
![Abbildung 10](workflows/openHAB_UmgebungsUI.png)

### ACS (AsTeRICs Configuration Suite)
Bei der ACS werden Elemente eines GUI in vorgefertigten Programmblöcken programmiert, diese sind in die Kategorien Sensors, Processors and Actuators unterteilt. Durch das Verknüpfen mit der ARE kann das erstellte Modell nutzbar gemacht und ausgeführt werden. Im GUI Editor lässt sich die Anordnung der zur Verfügung stehenden Elemente verändern. 
![Abbildung 11](workflows/ACS_Systemleiste_connect_to_ARE.png)
ACS lässt sich mit der ARE verbinden dazu muss die Anwendung ebenfalls gestartet werden und der lokale openHAB Server gestartet worden sein. Wenn das Modell fertig ist kann dieses über "Upload Model" auf die ARE übertragen und ausgeführt werden, es kann aber auch ein sich in der ARE befindende Modell lokal abgesichert werden mit "Download Model".
![Abbildung 12](workflows/ACS_GUI.png)
Hier lassen sich die verschiedenen Elemente beliebig anordnen.
![Abbildung 13](workflows/openHAB_ACS_cell.png)
openHAB Processor mit 3 Items: Temperatur, Licht und Jalousien
![Abbildung 14](workflows/ACS_ButtonGrid_properties.png)
Button Grid für die 3 Items

### ARE (AsTeRICs Runtime Environment)
Das in ACS erstellte Modell wird in die ARE hochgeladen und kann dann gestartet werden wodurch sich dann ein interaktives GUI öffnet. 
![Abbildung 15](workflows/ACS_Items-config.png)
Ausgeführtes ACS Modell in der ARE
### ACS Properties für Temperatur Slider
![Abbildung 16](workflows/ACS_Slider_properties.png)
## Dokumentation Demo Video

