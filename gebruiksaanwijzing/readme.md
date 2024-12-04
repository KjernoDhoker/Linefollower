# Gebruiksaanwijzing

### opladen / vervangen batterijen
het opladen gebeurd bij mij met een zelf gemaakte powerbank dat ik al liggen had. Deze had ik gemaakt met een oude fiets batterij.

bij het vervangen van de batterij moet je er op letten dat je de + naar de + zijde doet en de - naar de - zijde.

### draadloze communicatie
#### verbinding maken
gebruik de app serial bluetooth terminal op je android toestel. verbind via deze app via bluetooth met je esp 32.

#### commando's
debug: Stuurt alle ingestelde parameters en berekende calculation time terug.
run: Start de robot.
stop: stopt de robot
set cycle: [µs] Stelt de cycle time in van de robot.
set power: [0..255] Stelt de maximum power van de robot in.
set diff: [0..1] Stelt de verschil in power tussen de motoren in bochten
set kp: [0..] Stelt de propertionele correctie van de fout in.
set ki: [0..] Stelt de integrale correctie van de fout in.
set kd: [0..] Stelt de differentiële correctie van de fout in.
calibrate black: Stelt de waardes gelezen door de sensor in als zwart.
calibrate white: Stelt de waardes gelezen door de sensor in als wit.

### kalibratie
Er moet worden gekalibreerd omdat er een verschil is tussen de verschillende sensoren, door een tolerantie op de onderdelen, wat eigen is aan productie.
Positioneer de sensoren boven een zwart vlak en voer het commando calibrate black uit in de Terminal.
Breng vervolgens de sensoren boven een wit vlak en voer het commando calibrate white uit. De
sensoren zijn nu gekalibreerd. 

### settings
cycle time: 200
power: 300
Diff: 0.50
Kp: 15
Ki: 0
Kd: 0.8
