# Installation des Spiels

1. Laden Sie sich die Engine runter. Diese finden sie [hier](https://defold.com/download/). Alternativ ist, falls vorhanden, auch eine Installation über [Steam](https://store.steampowered.com/about/) möglich.
2. Entpacken Sie den ZIP-kompripierten Ordner und öffnen Sie diesen. Klicken Sie auf die Datei Defold.exe. Nun öffnet sich eine Übersichsseite der Engine.
3. Fügen Sie das Projekt der Engine hinzu. Klicken Sie hierfür im unteren Reiter auf `Open From Disk`. Navigieren Sie nun bis zur Wurzelebene des Projektordners und wählen sie die Datei `game.project`aus. Nun öffnet sich das Spiel in einem neuen Fenster.
4. Nun müssen die Dependencies heruntergeladen werden. Klicken sie hierfür in der oberen Menüleiste auf `Project` und dann auf `Fetch Libraries`. Nun erscheinen zwei weitere Ordner (mit Puzzlesymbol) *rendercam* und *defos*. 
5. Das Spiel kann nun gestartet werden, indem nun wieder in der oberen Menüleiste auf `Project` geklickt wird und die Einträge `Build` oder `Rebuild` selektiert werden.

# Spielmechanik
Das Spiel besteht aus drei Leveln, die jeweils eine erfüllbare Mission besitzen. Am Ende jedes Levels, außer des Finallevels, erscheint ein Portal, welches die Spielfigur zum nächsten Level führt. Die Missionen werden von Level zu Level immer schwieriger. Der Spieler bewegt die Spielfigur mittels WASD-Tasten. Die Spielfugar kann geradeaus, nach unten, links, rechts, aber auch in eine kombinierte Richtung laufen *z. B. schräg nach oben rechts* laufen. Somit ergeben sich insgesamt acht Bewegungsrichtungen.

Folgende Missionen müssen in den Levels erfüllt werden:
1. Zehn Gegner eliminieren
2. Vier Münzen finden
3. Eine Minute überleben

Das Leben der Spielfigur ist begrenzt, weshalb die Spielfigur den Gegnern ausweichen muss und diese eliminieren kann. Bei den Gegnern erscheint eine Lebensanzeige, sobald sie Schaden genommen haben. Es existieren folgende Arten von Gegnern, die bei Kollision Schaden verursachen:
- Mumie: Diese läuft von oben nach unten und ist statisch im Spiellayout gesetzt. Alle anderen Gegner werden dynamisch an zugewiesene Spawnpoints erzeugt. Einer Mumie kann nicht angegriffen werden.
- Schlange: Diese läuft auf den Gegner zu, sobald es im Sichtfeld der Spielfigur ist (also keine Wand dazwischen ist).
- Skorpion: Diese läuft unabhängig von der Position des Spielers. Wenn er mit einer Wand kollidiert, dann dreht er sich entsprechend um 90°. Dieser Gegner ist jedoch nicht zu verlässigen, da dieser im Zwei-Sekunden-Intervall ein Gift in Richtung der Spielfigur schießt. Das Gift wird nur geschossen, wenn die Spielfigur im Sichtfeld des Skorpions ist. Besonders im letzten Level ist dies eine schwere Herausforderung.

Um einen Gegner zu eliminieren, können folgende Waffen genutzt werden:
- Schwert: Dies kann für den Nahkampf genutzt werden, indem es mit einem Gegner (außer der Mumie) kollidiert. Eine entsprechende Kollision führt ebenso zu einem Knockback (Gegner werden nach hinten geschmettert) und einem Cooldown, bis der nächste Schwert-Angriff erfolgen kann.
- Raketenwerfer: Dieser wird von der Spielfigur aktiviert, indem die Space-Taste oder die linke Maustaste aktiviert wird. Die Rakete wird in Richtung des Mauszeiger geworfen und hat eine maximale Reichweite. Sobald es mit einem Gegner oder einer Wand kollidiert, explodiert diese. Alle Gegner im Umkreis erhalten dabei einen festgelegten Schaden. Der Raketenwerfer besitzt ebenfalls einen Cooldown.

Während des Spiels können auch Items gesammelt werden. Diese haben positive Auswirkungen für den Spieler. Items werden von Gegnern mit einer festgelegten individuellen Wahrscheinlichkeit gedroppt, wenn diese eliminiert wurden. Folgende Items und Fähigkeiten existieren:
- Bogen: Hierdurch wird die Fernkampfsangriffsgeschwindigkeit erhöht
- Dolch: Erhöht die Angriffsgeschwindigkeit im Nahkampf
- Schuh: Erhöhung der Bewegungsgeschwindigkeit
- Herz: Das Leben wird um 10 HP wiederhergestellt. Die maximale Anzahl an Leben ist begrenzt

Desweiteren kann man im Level 2 vier Münzen finden. Diese werden nicht von Gegnern gedroppt, sondern werden an zufälligen Positionen im Level verteilt.

Der Spieler bewegt sich in einer Spielwelt, die durch Wände abgegrenzt ist. Es existieren in der Spielumgebung weitere Elemente, mit denen der Spieler interagieren kann:
- Nebel: Der Spieler ist langsamer, während er durch den Nebel läuft. Hier ist jedoch Vorsicht geboten, da die Gegner nicht beeinflusst werden!
- Portal: Bringt den Spieler ins nächste Level. Beim Levelübergang wird das Leben der Spielfigur wieder aufgefüllt.
- Portal-Nebel: Der Spieler kann hier sehen, wo potentiell ein Portal spawnen könnte

Der Faktor Zeit spielt eine wichtige Rolle in dem Spiel. Denn mit fortschreitender Zeit, wird der Schwierigkeitsgrad immer höher. Die Spawnrate der Gegner steigt nämlich stetig an - ein Vorteil für den Spieler ist aber auch, dass mehr Items in der Spielwelt spawnen. Im letzten Level gibt es eine zusätzliche Spawnrate, die unabhängig von der Zeit ist. Zu schnell sein, ist daher womöglich auch nicht die ideale Strategie.

Diagramme zum detaillierten Spielablauf können Sie der Präsentation entnehmen.

Nun wo das Konzept klar ist, kann der Spielspaß sofort beginnen - Viel Spaß!

# Referenzierte Medien
Folgende aus dem Internet entnommenen freiverfügbaren Medien wurden verwendet:
- Spielfigur des Spielers (Bild): https://craftpix.net/freebies/free-homeless-character-sprite-sheets-pixel-art/
- Tileset für Level 1 und 2: https://0x72.itch.io/dungeontileset-ii
- Tileset für Level 3: https://craftpix.net/freebies/free-undead-tileset-top-down-pixel-art/
- Raketenwerfer (Bild) wurden aus einem Beispielprojekt von Defold übernommen: https://github.com/defold/tutorial-war-battles

Folgende Grafiken wurden von Linus Pöppelmann angefertigt:
- Mumie
- Schlange
- Skorpion inkl. Skorpiongift
- Schwert
- Bogen
- Dolch
- Schuh
- Herz
- Münze
- Nebel
- Portal-Nebel
- Portal
- Lebensanzeige

# Referenzierte externe Bibliotheken
- rendercam: https://github.com/rgrams/rendercam/archive/1.0.3.zip
- defos: https://github.com/subsoap/defos/archive/refs/tags/v2.7.1.zip


