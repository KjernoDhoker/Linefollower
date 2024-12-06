# Instructable

Bij dit project bouwen we een Line Following Robot die een zwarte lijn op een wit parcours kan volgen. Het omvat mechanische montage, elektrische bedrading, en softwareontwikkeling. Deze uitgebreide instructable leidt je stap voor stap door het proces.

Stap 1: Materialen en Gereedschappen

1\.1 Materiaalcontrole

Controleer alle onderdelen in de BoM en zet ze op een werkoppervlak. Test de motoren en sensoren voor gebruik.

1\.2 Gereedschappen Voorbereiden

* Soldeerbout : Voor permanente verbindingen.
* Multimeter : Voor spanningsmetingen.
* Schroevendraaier : Voor montage van bouten en moeren.
* Lijm : Voor bevestiging van lichte onderdelen.
* Laptop met Arduino IDE : Voor softwareontwikkeling.

Stap 2: Mechanische montage

2\.1 Chassisprinten

* Gebruik een STL-bestand voor een 3D-geprint chassis.
* Zorg ervoor dat het chassis binnen de maximale afmetingen van 12x12 cm past.

2\.2 Motoren Bevestigen

1. Bevestig de GA12-N20 motoren aan de daarvoor voorziene punten op het chassis.
1. Gebruik M3-bouten en moeren voor een stevige bevestiging.
1. Controleer de uitlijning van de motorassen.

2\.3 Wielen Monteren

1. Klik op de schroef van de rubberen wielen stevig op de motorassen.
1. Controleer of ze soepel draaien zonder speling.

2\.4 Zwenkwiel Toevoegen

* Bevestig het zelfklevende zwenkwiel aan de voorkant van het chassis voor stabiliteit.

2\.5 Batterijhouder Installeren

* Plaats de 18650 batterijhouder op een centrale locatie om het zwaartepunt in balans te houden.

Stap 3: Elektrische Installatie

3\.1 Elektronisch Schema Volgen

Gebruik een schema waarin:

* Motoren zijn verbonden met de H-brug.
* Reflectiesensoren zijn aangesloten op analoge pinnen van de ESP32.
* Voeding van batterijen direct naar de motor driver gaat.

3\.2 Motor Driver Aansluiten

1. Verbind de DRV8833 motordriver met de ESP32 GPIO-pinnen.
1. Sluit de motoren aan op de uitvoerpoorten van de motor driver.
1. Gebruik een spanningsregelaar indien nodig om 5V of 3.3V te genereren.

3\.3 Reflectiesensoren

1. Bevestig de QTR-8A reflectiesensorarray op het chassis, loodrecht op de rijrichting.
1. Verbind de sensoren met analoge poorten van de ESP32.

3\.4 Microcontroller

1. Plaats de ESP32 op een locatie.
1. Sluit de ESP32 aan op de H-brug en sensoren.
1. Voeg een power-on LED en een schuifschakelaar toe aan het circuit.

Stap 4: Het Programma Laden op de ESP32

Een cruciale stap bij het maken van je Line Following Robot is het uploaden van de code naar de ESP32- microcontroller via de Arduino IDE. Volg deze ingewikkelde stappen:

4\.1 Arduino IDE voorbereiden

1. Arduino IDE Installeren
- Download de Arduino IDE en installeer deze op je computer.

2\. ESP32 Board Manager Toevoegen

- Open de Arduino IDE. Ga naar Bestand > Voorkeuren .
- Zoek het veld Extra Boards Manager-URL's en voeg deze URL toe:
  https://dl.espressif.com/dl/package_esp32_index.json

Arduino

Code kopiëren

- Klik op OK .

3\. Bestuursmanager Installateurs

- Ga naar Hulpmiddelen > Bestuur > Bestuursmanager .
- Zoek naar ESP32 en klik op Installeren .

4\.2 ESP32 configureren in Arduino IDE

1. Selecteer het ESP32-bord
- Ga naar Hulpmiddelen > Bord > ESP32 Arduino > ESP32 Dev Module .

2\. Selecteer de Poort

- Verbind de ESP32 met je computer via een USB-kabel.
- Ga naar Hulpmiddelen > Poort en selecteer de COM-poort waarop je ESP32 is aangesloten.

3\. Stel de uploadparameters in

- Zorg ervoor dat de volgende instellingen correct zijn:
* Uploadsnelheid: 115200.

4\.3 Code downloaden

1. Downloaden vanuit github
1. Bibliotheken Toevoegen
- Ga naar Schets > Bibliotheek opnemen > Bibliotheken beheren .
- Zoek en installeer de volgende bibliotheken:
* PololuQTRSensors voor de reflectiesensor.
* PID\_v1 voor de PID-regelaar (optioneel).

4\.4 Code uploaden naar de ESP32

1. Upload de code
- Klik op het pijltje Uploaden (??) in de Arduino IDE.
- Tijdens het uploaden kan de ESP32 in flashmodus gezet worden:
* Houd de BOOT-knop van de ESP32 ingedrukt totdat het uploadproces begint.

2\. Controleer de Serial Monitor

- Na het uploaden kun je de uitvoer bekijken:
* Ga naar Hulpmiddelen > Seriële Monitor en stel de baudrate in op 115200 .

4\.5 Foutopsporing

* Foutmelding: “Kan geen verbinding maken met ESP32: Time-out bij wachten op pakketheader.”
- Houd de BOOT-knop langer ingedrukt tijdens het uploadproces.
* Geen poort zichtbaar: Controleer of de juiste driver defect is voor de USB-kabel.

Stap 5: Testen en debuggen

5\.1 Testen op het parcours

1. Plaats de robot op een wit parcours met een zwarte lijn.
1. Controleer of de robot de lijn correct detecteert en volgt.

5\.2 Probleemoplossing

* Onstabiele beweging: Pas de PID-parameters (IkP,Iki,IkDK\_p, K\_i, K\_dIkP?,Iki?,IkD?) aan.
* Sensorproblemen: Controleer of de sensoren op de juiste hoogte staan.

Stap 6: Optimalisatie

6\.1 Snelheid Verhogen

* Test hogere motorspanningen en pas de PID-parameters aan.

6\.2 Draadloze communicatie

1. Gebruik de WiFi-module op de ESP32 om instellingen draadloos aan te passen.
1. Bouw een webinterface om PID-waarden en motorsnelheden te wijzigen.

