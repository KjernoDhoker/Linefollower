# Instructable


Lijnvolgende robot: intelligente Instructable
Inleiding
Bij dit project bouwen we een Line Following Robot die een zwarte lijn op een wit parcours kan volgen. Het omvat mechanische montage, elektrische bedrading, en softwareontwikkeling. Deze uitgebreide instructable leidt je stap voor stap door het proces.

Stuklijst (BoM)
Nr	Naam	Omschrijving	Aantal	Prijs/stuk	Subtotaal
|       1| QTR-8A reflectance sensor array- analog - Pololu 960   | line following sensor           |  nieuw         |    €10          |  1    |   €10        |
|         2| zelfklevend zwenkwiel|24-4 Stuks Zelfklevende Zwenkwielen 360 Graden Rotatie Zwenkwielen Mini Wielen Voor Het Verplaatsen Van Meubelen Caster Katrol|nieuw|0,93| 1| €0.93| 
|         3| 18650 Acculader 1/2/4 Sleuven Dual 18650 Opladen 3.7V Oplaadbare Lithium Batterij Usb Oplader Voor 16340 14500 18650 26650 | baterij oplader| nieuw|€0.93|1|€0.93| 
|         4|GA12-N20 Tandwielmotor Dc 3V/6V/12V N20 Mini Micro Metalen Tandwielmotor Met Tandwiel Dc Motoren 15/30/50/60/100/200/300/500/1000Rpm|DC motoren|nieuw|€3.41| 2| €6.28|
|         5|Micro Schuifschakelaar Spdt 3 Pin 5 Posities Mini Ss12f15 Ss12f44 1p2t 3Mm 4Mm 5Mm 6Mm kleine Toggle Pcb Mount Terminal Voor Arduino|schuifschakelaar|nieuw|€0.93|1|€0.93|
|          6|10 Stks/partij D-Hole Rubber Wiel Geschikt Voor N20 Motor D As Band Auto Robot Diy Speelgoed Onderdelen|wielen voor motor|nieuw|€0.93 |1|€0.93 |
|          7|1 2 3 4 Slot Diy Batterijen Clip Houder Container Plastic 18650 Houder Doos Met Draad Lood Zwart Voor 18650 3.7V Batterij|batterij houder voor 2 baterijen|nieuw|€0.96|1|€0.96|
|          9|1-10PCS/ESP32 Development Board Type-C CP2102 WIFI Bluetooth Module Dual Core Draadloze Module ESP-WROOM-32 Uitbreidingskaart 38Pin|microcontroler ESP32|nieuw|€4.82|1|€4.28|
|          10|1-10 Stuks Drv8833 Motor Aandrijfmodule 1.5a Dual H Brug Dc Versnelling Motor Driver Controller Board Diy Kit|H brug DRV8833|nieuw|€5.41|1|€5.41|
|          12|A4988 Stepper Motor Driver Module Met Koellichaam Voor Arduino 3d Printer Reprap Cnc Machine Of Robotica|driver stappenmotor|nieuw|€5.72|1|€5.72|
|          13|Dupont Lijn 10/20/30/40Cm 40pin Mannelijk Naar Mannelijk + Mannelijk Naar Vrouwelijk En Vrouwelijk Naar Vrouwelijk Jumper Draad Dupont Kabel Voor Arduino Diy Kit|extra wires|nieuw|€2.03|1|€2.03|
|          14|lijm(tex 7)|secondenlijm voor componenten vast te hangen|recup| |1| |
|          15|bout|bout m3|recup| |1| |
|          16|moer|moer m3|recup| |1| |
|          17|onderstel|3D printer|school| |1| |

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
