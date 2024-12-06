# Instructable


Lijnvolgende robot: intelligente Instructable
Inleiding
Bij dit project bouwen we een Line Following Robot die een zwarte lijn op een wit parcours kan volgen. Het omvat mechanische montage, elektrische bedrading, en softwareontwikkeling. Deze uitgebreide instructable leidt je stap voor stap door het proces.

Stuklijst (BoM)
Nr	Naam	Omschrijving	Aantal	Prijs/stuk	Subtotaal
1	QTR-8A reflectiesensor	Lijnvolgende sensorarray	1	€ 10,00	€ 10,00
2	zelfklevend zwenkwiel	Stabiliteitswiel	1	€0,93	€0,93
3	GA12-N20 Tandwielmotor	6V Minimotor met tandwielreductie	2	€ 3,41	€ 6,82
4	18650 Batterijhouder	Voor 2 batterijen	1	€0,96	€0,96
5	ESP32-ontwikkelingsbord	Microcontroller met WiFi/Bluetooth	1	€4,82	€4,82
6	DRV8833-motorbesturing	Dubbele H-brug motorcontroller	1	€ 5,41	€ 5,41
7	Dupont Jumper-draden	Verbindingen	1 set	€ 2,03	€ 2,03
8	M3 Moeren en Bouten	Bevestigingsmateriaal	6 sets	Herstel	€0,00
9	Lijm en bevestiging	Voor montage van chassis en onderdelen	1	Herstel	€0,00
10	3D-geprint chassis	Op maat gemaakt chassis	1	School	€0,00
Stap 1: Materialen en Gereedschappen
1.1 Materiaalcontrole
Controleer alle onderdelen in de BoM en zet ze op een werkoppervlak. Test de motoren en sensoren voor gebruik.

1.2 Gereedschappen Voorbereiden
Soldeerbout : Voor permanente verbindingen.
Multimeter : Voor spanningsmetingen.
Schroevendraaier : Voor montage van bouten en moeren.
Lijm : Voor bevestiging van lichte onderdelen.
Laptop met Arduino IDE : Voor softwareontwikkeling.
Stap 2: Mechanische montage
2.1 Chassisprinten
Gebruik een STL-bestand voor een 3D-geprint chassis.
Zorg ervoor dat het chassis binnen de maximale afmetingen van 12x12 cm past.
2.2 Motoren Bevestigen
Bevestig de GA12-N20 motoren aan de daarvoor voorziene punten op het chassis.
Gebruik M3-bouten en moeren voor een stevige bevestiging.
Controleer de uitlijning van de motorassen.
2.3 Wielen Monteren
Klik op de schroef van de rubberen wielen stevig op de motorassen.
Controleer of ze soepel draaien zonder speling.
2.4 Zwenkwiel Toevoegen
Bevestig het zelfklevende zwenkwiel aan de voorkant van het chassis voor stabiliteit.
2.5 Batterijhouder Installeren
Plaats de 18650 batterijhouder op een centrale locatie om het zwaartepunt in balans te houden.
Stap 3: Elektrische Installatie
3.1 Elektronisch Schema Volgen
Gebruik een schema waarin:

Motoren zijn verbonden met de H-brug.
Reflectiesensoren zijn aangesloten op analoge pinnen van de ESP32.
Voeding van batterijen direct naar de motor driver gaat.
3.2 Motor Driver Aansluiten
Verbind de DRV8833 motordriver met de ESP32 GPIO-pinnen.
Sluit de motoren aan op de uitvoerpoorten van de motor driver.
Gebruik een spanningsregelaar indien nodig om 5V of 3.3V te genereren.
3.3 Reflectiesensoren
Bevestig de QTR-8A reflectiesensorarray op het chassis, loodrecht op de rijrichting.
Verbind de sensoren met analoge poorten van de ESP32.
3.4 Microcontroller
Plaats de ESP32 op een locatie.
Sluit de ESP32 aan op de H-brug en sensoren.
Voeg een power-on LED en een schuifschakelaar toe aan het circuit.
Stap 4: Software-installatie
4.1 Arduino IDE-configuratie
Voeg de ESP32 Board Manager toe via de instellingen in de Arduino IDE.
Installeer bibliotheken zoals PololuQTRSensors en een PID-controller bibliotheek .
4.2 Basiselementen Programmeren
Sensorkalibratie:
Schrijf een routine om de minimale en maximale waarden van de sensoren op wit en zwart te impliceren.
Motor Sturing:
Programmeur PWM-signalen voor de motorsnelheid en richting aan te passagiers.
PID-Regelaar:
Schrijf een PID-algoritme om defecte van de lijn te corrigeren.
Stap 5: Testen en debuggen
5.1 Testen op het parcours
Plaats de robot op een wit parcours met een zwarte lijn.
Controleer of de robot de lijn correct detecteert en volgt.
5.2 Probleemoplossing
Onstabiele beweging: Pas de PID-parameters (
Ik
𝑃
,
Ik
𝑖
,
Ik
𝐷
Ik 
P
​
 ,Ik 
i
​
 ,Ik 
D
​
 ) aan.
Sensorproblemen: Controleer of de sensoren op de juiste hoogte staan.
Stap 6: Optimalisatie
6.1 Snelheid Verhogen
Test hogere motorspanningen en pas de PID-parameters aan.
6.2 Draadloze communicatie
Gebruik de WiFi-module op de ESP32 om instellingen draadloos aan te passen.
Bouw een webinterface om PID-waarden en motorsnelheden te wijzigen.
