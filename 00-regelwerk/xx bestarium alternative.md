# Terranea - Monster-Datenbank

## Inhaltsverzeichnis

- [Datenbank-Struktur](#datenbank-struktur)
- [Monster-Liste](#monster-liste)
- [Suchfunktionen (Dataview-Queries)](#suchfunktionen)

---

## Datenbank-Struktur

```yaml
monsters:
  - id: eindeutige_id
    name: Monster-Name
    type: Bestie/Humanoid/Untoter/Dämon/Elementar
    difficulty: Minion/Standard/Elite/Champion/Boss/Legendär
    size: Klein/Mittel/Groß/Riesig
    
    # Attribute
    str: X | dex: X | con: X | int: X | wis: X | cha: X | magic: X (optional)
    
    # Kampfwerte
    hp: X | mp: X (optional) | armor: X | initiative: X | movement: X
    
    # Angriffe
    attacks: [{name, type, hit, damage, range, special}]
    
    # Zauber (optional)
    spells: [{name, cost, difficulty, damage/effect, range, special}]
    
    # Verteidigung & Fähigkeiten
    dodge: X | skills: [] | abilities: []
    
    # Resistenzen
    resistant: [] | weak: [] | immune: []
    
    # Verhalten & Beute
    behavior: "..." | loot: "..." | xp: X | description: "..."
```

---

## Monster-Liste

````yaml
---
monsters:
  # ========================================
  # MINIONS (Level 1-3)
  # ========================================
  
  - id: waldwolf
    name: Waldwolf
    type: Bestie
    difficulty: Minion
    size: Mittel
    str: 8
    dex: 10
    con: 6
    int: 2
    wis: 6
    cha: 4
    hp: 12
    armor: 2
    initiative: 5
    movement: 12
    attacks:
      - name: Biss
        type: Nahkampf
        hit: 4
        damage: 1W6+2
        range: Nahkampf
        special: "Bei Krit (12): Zu Boden werfen (STR-Probe 14)"
      - name: Sprung-Angriff
        type: Nahkampf
        hit: 5
        damage: 1W6+1
        range: 5m Sprung
        special: "+2 Treffer wenn Ziel nicht aufmerksam"
    dodge: 5
    skills:
      - "Nahkampf 2"
    abilities:
      - "Rudeltaktik: +2 Angriff pro Wolf im Nahkampf (max +6)"
      - "Nachtjäger: Keine Mali bei Dunkelheit"
      - "Fährtenlesen: Verfolgt Beute über große Distanzen"
    resistant: [Kälte]
    weak: [Feuer]
    immune: []
    behavior: "Greift im Rudel an, umzingelt Gegner, nutzt Geschwindigkeit. Einzelner Wolf flieht bei unter 5 HP."
    loot: "Wolfsfell (5S), Wolfszähne (2S)"
    xp: 5
    description: "Grau-braunes Raubtier, lebt in Rudeln von 4-8 Tieren in Wäldern"

  - id: riesige_ratte
    name: Riesige Ratte
    type: Bestie
    difficulty: Minion
    size: Klein
    str: 4
    dex: 12
    con: 5
    int: 2
    wis: 5
    cha: 2
    hp: 8
    armor: 1
    initiative: 6
    movement: 10
    attacks:
      - name: Biss
        type: Nahkampf
        hit: 2
        damage: 1W6
        range: Nahkampf
        special: "Bei Treffer: Gift (Konsti-RW 12 oder 1W6 Schaden/Runde für 2 Runden)"
    dodge: 6
    skills:
      - "Nahkampf 1"
    abilities:
      - "Schwarmtaktik: +1 Angriff pro Ratte (max +4)"
      - "Dunkelheit: Perfekte Sicht in Dunkelheit"
      - "Krankheitsüberträger: 20% Chance, Ziel infiziert"
    resistant: [Gift]
    weak: []
    immune: []
    behavior: "Greift in Schwärmen an, beißt und flieht. Bevorzugt geschwächte Ziele."
    loot: "Rattenfell (2K), manchmal kleine Wertgegenstände"
    xp: 3
    description: "Hundsgroße Ratten in Kanalisation und Ruinen, gefährlich in Massen"

  - id: goblin
    name: Goblin
    type: Humanoid
    difficulty: Minion
    size: Klein
    str: 5
    dex: 10
    con: 6
    int: 6
    wis: 5
    cha: 4
    hp: 10
    armor: 2
    initiative: 5
    movement: 8
    attacks:
      - name: Kurzschwert
        type: Nahkampf
        hit: 3
        damage: 1W6+1
        range: Nahkampf
        special: null
      - name: Kurzbogen
        type: Fernkampf
        hit: 5
        damage: 1W6
        range: 20m
        special: null
    dodge: 5
    skills:
      - "Nahkampf 1"
      - "Fernkampf 2"
    abilities:
      - "Feige: -2 auf alle Proben wenn allein"
      - "Hinterhältig: +2 Angriff aus Hinterhalt"
      - "Klein: +2 auf Verstecken"
    resistant: []
    weak: []
    immune: []
    behavior: "Greift aus Hinterhalten, nutzt Fernkampf. Flieht wenn Anführer stirbt oder Gruppe unter 50%."
    loot: "Kurzschwert (1G), Kurzbogen (3G), 1W6 Kupfer"
    xp: 5
    description: "Kleine, grüne Humanoide mit spitzen Ohren. Feige aber zahlreich. Leben in Stämmen."

  - id: skelett_krieger
    name: Skelett-Krieger
    type: Untoter
    difficulty: Minion
    size: Mittel
    str: 8
    dex: 8
    con: 6
    int: 1
    wis: 3
    cha: 1
    hp: 14
    armor: 3
    initiative: 4
    movement: 8
    attacks:
      - name: Rostige Klinge
        type: Nahkampf
        hit: 4
        damage: 1W6+2
        range: Nahkampf
        special: "Bei Treffer: 10% Chance auf Wundinfektion"
      - name: Knochenfaust
        type: Nahkampf
        hit: 4
        damage: 1W6+1
        range: Nahkampf
        special: null
    dodge: 4
    skills:
      - "Nahkampf 2"
    abilities:
      - "Untot: Immun gegen Gift, Krankheit, Schlaf, Angst"
      - "Keine Schmerzen: Ignoriert Mali durch Verletzungen"
      - "Knochenstruktur: Stumpfwaffen -2 Schaden"
    resistant: [Stumpf, Kälte]
    weak: [Heilig, Feuer]
    immune: [Gift, Krankheit, Schlaf, Angst]
    behavior: "Greift ohne Selbsterhaltungstrieb an. Folgt Befehlen bis zur Zerstörung."
    loot: "Verrostete Waffe (5K), Knochen (2K), manchmal alte Münzen (1W6 K)"
    xp: 6
    description: "Animierte Knochen in Rüstungsresten. Folgt Nekromanten oder alten Befehlen."

  - id: riesige_spinne
    name: Riesige Spinne
    type: Bestie
    difficulty: Minion
    size: Mittel
    str: 6
    dex: 12
    con: 6
    int: 1
    wis: 8
    cha: 2
    hp: 11
    armor: 2
    initiative: 6
    movement: 10
    attacks:
      - name: Giftbiss
        type: Nahkampf
        hit: 3
        damage: 1W6
        range: Nahkampf
        special: "Gift: Konsti-RW 14 oder 1W6+2 Giftschaden sofort + gelähmt für 1 Runde"
      - name: Netz
        type: Fernkampf
        hit: 6
        damage: null
        range: 10m
        special: "Ziel gefesselt, STR-Probe 14 zum Befreien"
    dodge: 6
    skills:
      - "Nahkampf 1"
    abilities:
      - "Wandklettern: Kann an Wänden/Decken laufen"
      - "Netzsinn: Spürt Bewegungen in ihrem Netz (20m Radius)"
      - "Hinterhalt: +4 auf Angriff aus versteckter Position"
    resistant: [Gift]
    weak: [Feuer]
    immune: []
    behavior: "Lauert in Netzen, fesselt Beute und vergiftet sie. Flieht wenn Netz zerstört wird."
    loot: "Spinnengift (15G), Spinnenseide (5S), Spinnenbeine (3S)"
    xp: 6
    description: "Pferdgroße Spinne mit schwarzem Körper. Baut Netze in Höhlen und Ruinen."

  # ========================================
  # STANDARD (Level 2-5)
  # ========================================

  - id: ork_krieger
    name: Ork-Krieger
    type: Humanoid
    difficulty: Standard
    size: Groß
    str: 12
    dex: 6
    con: 10
    int: 4
    wis: 4
    cha: 3
    hp: 25
    armor: 4
    initiative: 3
    movement: 8
    attacks:
      - name: Großaxt
        type: Nahkampf
        hit: 9
        damage: 2W6+4
        range: Nahkampf
        special: "Volle Kraft: -2 Treffer, aber +1W6 Schaden"
      - name: Wurfspeer
        type: Fernkampf
        hit: 5
        damage: 1W6+4
        range: 15m
        special: "Nur 1-2 Speere"
    dodge: 3
    skills:
      - "Nahkampf 3"
      - "Fernkampf 2"
    abilities:
      - "Wutanfall: Bei unter 10 LP: +2 Angriff, -2 Verteidigung"
      - "Schmerzresistenz: Ignoriert Verletzungs-Mali bis 5 LP"
      - "Ork-Stärke: Kann schwere Waffen ohne Mali führen"
    resistant: [Gift]
    weak: [Heilig]
    immune: []
    behavior: "Aggressiv, stürmt direkt auf Gegner zu. Nutzt rohe Kraft. Kämpft bis zum Tod bei Häuptling in Sicht."
    loot: "Großaxt (4G), Lederrüstung (5G), Schild (1G), 1W6 Silber"
    xp: 15
    description: "Muskulöser grünhäutiger Krieger mit Hauern. Frontkämpfer der Ork-Armeen."

  - id: bandit
    name: Bandit
    type: Humanoid
    difficulty: Standard
    size: Mittel
    str: 8
    dex: 10
    con: 8
    int: 7
    wis: 6
    cha: 6
    hp: 18
    armor: 2
    initiative: 5
    movement: 10
    attacks:
      - name: Kurzschwert
        type: Nahkampf
        hit: 6
        damage: 1W6+2
        range: Nahkampf
        special: null
      - name: Kurzbogen
        type: Fernkampf
        hit: 7
        damage: 1W6+2
        range: 20m
        special: null
    dodge: 5
    skills:
      - "Nahkampf 2"
      - "Fernkampf 3"
      - "Schleichen 2"
    abilities:
      - "Hinterhalt: +2 Angriff wenn aus Versteck"
      - "Feige: Flieht bei unter 30% HP oder wenn Anführer stirbt"
      - "Straßenklug: +2 auf Täuschung und Einschüchtern in Städten"
    resistant: []
    weak: []
    immune: []
    behavior: "Greift aus Hinterhalten, bevorzugt Fernkampf. Flieht wenn Kampf schlecht läuft. Verhandelt wenn unterlegen."
    loot: "Kurzschwert (1G), Kurzbogen (3G), Lederrüstung (5G), 1W6+2 Silber"
    xp: 12
    description: "Gesetzloser Räuber, lauert auf Handelsstraßen. Arbeitet in Banden von 3-8 Mitgliedern."

  - id: zombie
    name: Zombie
    type: Untoter
    difficulty: Standard
    size: Mittel
    str: 10
    dex: 4
    con: 12
    int: 1
    wis: 2
    cha: 1
    hp: 22
    armor: 1
    initiative: 2
    movement: 6
    attacks:
      - name: Fäuste
        type: Nahkampf
        hit: 5
        damage: 1W6+3
        range: Nahkampf
        special: "Bei Krit: Umklammerung (STR-Probe 14 zum Befreien)"
      - name: Biss
        type: Nahkampf
        hit: 5
        damage: 1W6+2
        range: Nahkampf
        special: "Nur wenn Ziel umklammert. Risiko: Zombifizierung (Konsti-RW 16)"
    dodge: 2
    skills:
      - "Nahkampf 2"
    abilities:
      - "Untot: Immun gegen Gift, Krankheit, Schlaf, Angst"
      - "Keine Schmerzen: Ignoriert alle Verletzungs-Mali"
      - "Zombifizierung: Gebissene müssen RW schaffen oder werden bei Tod zu Zombies"
      - "Langsam aber unaufhaltsam: Wird nicht müde, verfolgt endlos"
    resistant: [Stumpf, Kälte]
    weak: [Heilig, Feuer]
    immune: [Gift, Krankheit, Schlaf, Angst]
    behavior: "Bewegt sich langsam auf Lebende zu. Umklammert und beißt. Kein Selbsterhaltungstrieb."
    loot: "Zerfetzte Kleidung (wertlos), manchmal alte Gegenstände (1W6 K)"
    xp: 14
    description: "Verwester Untoter, langsam aber gefährlich. Überträgt Zombifizierung durch Biss."

  - id: ork_schamane
    name: Ork-Schamane
    type: Humanoid
    difficulty: Standard
    size: Mittel
    str: 8
    dex: 6
    con: 10
    int: 9
    wis: 10
    cha: 6
    magic: 6
    hp: 22
    mp: 18
    armor: 3
    initiative: 3
    movement: 8
    attacks:
      - name: Schamanen-Stab
        type: Nahkampf
        hit: 4
        damage: 1W6+1
        range: Nahkampf
        special: null
    spells:
      - name: Feuerball
        cost: 4 MP
        difficulty: 14
        damage: 1W6+2
        range: 20m
        special: "Flächenschaden 3m Radius"
      - name: Ork-Stärkung
        cost: 3 MP
        difficulty: 12
        effect: "+2 Stärke für 1 Ork, 10 Min"
        range: 10m
        special: null
      - name: Kleine Heilung
        cost: 2 MP
        difficulty: 10
        effect: "Heilt 1W6 LP"
        range: Berührung
        special: null
    dodge: 3
    skills:
      - "Nahkampf 1"
      - "Magie 4 (Feuermagie 2, Shaper-Magie 1)"
    abilities:
      - "Schamanische Trance: +2 auf Zauber wenn unter 50% HP"
      - "Ork-Stärke: Ignoriert Erschöpfung"
      - "Stammesführung: Orks in 10m ignorieren Moral-Checks"
    resistant: [Gift]
    weak: [Heilig]
    immune: []
    behavior: "Bleibt hinten, unterstützt Krieger mit Magie. Feuerball gegen Gruppen, heilt Verwundete. Flieht wenn allein."
    loot: "Schamanen-Stab (10G), Zauberkomponenten (5G), 1W6 Silber, Manatrank (5G)"
    xp: 20
    description: "Ork-Magier mit Kriegsbemalung. Nutzt primitive Elementarmagie und Stärkungszauber."

  - id: ghul
    name: Ghul
    type: Untoter
    difficulty: Standard
    size: Mittel
    str: 10
    dex: 10
    con: 8
    int: 4
    wis: 6
    cha: 3
    hp: 20
    armor: 2
    initiative: 5
    movement: 10
    attacks:
      - name: Klauen
        type: Nahkampf
        hit: 5
        damage: 1W6+3
        range: Nahkampf
        special: "Bei Treffer: Lähmungsgift (Konsti-RW 14 oder gelähmt 1 Runde)"
      - name: Biss
        type: Nahkampf
        hit: 5
        damage: 1W6+2
        range: Nahkampf
        special: "Heilt Ghul um die Hälfte des Schadens"
    dodge: 5
    skills:
      - "Nahkampf 3"
    abilities:
      - "Untot: Immun gegen Gift, Krankheit, Schlaf, Angst"
      - "Leichengeruch: Lebende müssen Willens-RW 12 oder -2 auf alle Proben (10 Min)"
      - "Kannibale: Heilt 1W6 LP wenn er Leiche isst (1 Aktion)"
    resistant: [Gift, Kälte]
    weak: [Heilig, Feuer]
    immune: [Gift, Krankheit, Schlaf, Angst]
    behavior: "Lauert auf Friedhöfen, greift Einzelne an. Versucht zu lähmen und zu fressen. Flieht bei unter 5 LP."
    loot: "Ghul-Klauen (8G - Alchemie), verfaulte Reste (wertlos)"
    xp: 16
    description: "Verwester Untoter mit langen Klauen. Frisst Leichen, lähmt Lebende mit Gift."

  # ========================================
  # ELITE (Level 4-7)
  # ========================================

  - id: werwolf
    name: Werwolf
    type: Bestie
    difficulty: Elite
    size: Groß
    str: 14
    dex: 12
    con: 12
    int: 6
    wis: 8
    cha: 4
    hp: 45
    armor: 3
    initiative: 6
    movement: 14
    attacks:
      - name: Krallen
        type: Nahkampf
        hit: 9
        damage: 2W6+3
        range: Nahkampf
        special: "Kann 2x pro Runde angreifen"
      - name: Biss
        type: Nahkampf
        hit: 9
        damage: 2W6+4
        range: Nahkampf
        special: "Bei Treffer: Lykanthropie (Konsti-RW 18 oder infiziert)"
    dodge: 6
    skills:
      - "Nahkampf 5"
      - "Schleichen 3"
    abilities:
      - "Regeneration: +3 LP pro Runde (außer Silber/Feuer-Schaden)"
      - "Lykanthropie: Gebissene werden bei Vollmond zu Werwölfen"
      - "Nur Silber verletzt: Normale Waffen halber Schaden"
      - "Wolfssinne: +4 auf Wahrnehmung, riecht Blut auf 1km"
    resistant: [Normal-Waffen]
    weak: [Silber, Feuer]
    immune: []
    behavior: "Jagt aggressiv, nutzt Geschwindigkeit. Zwei Krallen-Angriffe, dann Biss. Regeneriert während Kampf."
    loot: "Werwolf-Fell (50G), Werwolf-Zahn (30G), manchmal menschliche Ausrüstung"
    xp: 40
    description: "Verfluchter Mensch in Wolfsgestalt. 2,5m groß, silbernes Fell, leuchtend gelbe Augen."

  - id: ork_haeuptling
    name: Ork-Häuptling
    type: Humanoid
    difficulty: Elite
    size: Riesig
    str: 14
    dex: 8
    con: 12
    int: 6
    wis: 6
    cha: 8
    hp: 55
    armor: 6
    initiative: 4
    movement: 10
    attacks:
      - name: Zweihand-Kriegsaxt "Schädelbrecher"
        type: Nahkampf
        hit: 12
        damage: 2W6+6
        range: Nahkampf
        special: "Mächtiger Schlag (1x/Kampf): 3W6+8 Schaden, -4 Verteidigung diese Runde"
      - name: Spalten
        type: Nahkampf
        hit: 12
        damage: 2W6+6
        range: Nahkampf
        special: "Bei Krit (12): Ignoriert Rüstung"
    spells:
      - name: Kriegsschrei
        cost: null
        difficulty: null
        effect: "Verbündete +2 Angriff (3 Runden), Gegner Willens-RW 16 oder -2 alle Proben (2 Runden)"
        range: 15m Radius
        special: "1x pro Kampf, freie Aktion"
    dodge: 4
    skills:
      - "Nahkampf 5 (Zweihandwaffen 4)"
      - "Einschüchterung 4"
      - "Taktik 2"
    abilities:
      - "Berserker-Wut: Bei unter 20 LP: +4 Angriff, +1W6 Schaden, -3 Verteidigung"
      - "Alphastellung: Orks in 20m +1 Moral"
      - "Kampferfahren: +2 Initiative"
      - "Legendäre Zähigkeit: Bei 0 LP einmal RW 14, bei Erfolg bleibt bei 1 LP"
    resistant: [Gift, Angst]
    weak: [Heilig]
    immune: [Einschüchterung]
    behavior: "Führt von vorne, nutzt Kriegsschrei zu Beginn. Stürmt auf stärksten Gegner. Bei unter 20 LP: Berserker."
    loot: "Schädelbrecher (+2 Schaden, 150G), Schuppenpanzer (50G), Häuptlings-Helm (20G), Runen-Talisman (+1 STR, 100G), 2W6 Gold"
    xp: 50
    description: "Riesiger Ork (2,3m), vernarbte dunkelgrüne Haut, rote Augen. Trägt Drachenschädel-Helm."

  - id: eisgolem
    name: Eisgolem
    type: Elementar
    difficulty: Elite
    size: Groß
    str: 16
    dex: 6
    con: 14
    int: 2
    wis: 4
    cha: 1
    hp: 50
    armor: 8
    initiative: 3
    movement: 8
    attacks:
      - name: Eisfaust
        type: Nahkampf
        hit: 8
        damage: 2W6+5
        range: Nahkampf
        special: "Bei Treffer: Verlangsamt (Bewegung halbiert, 2 Runden)"
      - name: Eisatem
        type: Fernkampf
        hit: null
        damage: 2W6+3
        range: Kegel 10m
        special: "Alle in Kegel: Reflex-RW 16 oder Schaden + Verlangsamt (3 Runden). 1x alle 3 Runden"
    dodge: 3
    skills: []
    abilities:
      - "Elementar: Immun gegen Gift, Krankheit, Schlaf, mentale Effekte"
      - "Eisige Präsenz: Alle in 5m nehmen 1 Kälteschaden/Runde"
      - "Eisige Rüstung: Nahkampf-Angreifer nehmen 1W6 Kälteschaden"
      - "Wiederaufbau: Wenn zerstört, kann nach 1 Stunde in kalter Umgebung regenerieren"
    resistant: [Kälte, Stumpf, Stich]
    weak: [Feuer]
    immune: [Gift, Krankheit, Schlaf, Gedankenkontrolle, Kälte]
    behavior: "Langsam aber unaufhaltsam. Nutzt Eisatem gegen Gruppen. Greift nächstes Ziel an. Keine Taktik."
    loot: "Eis-Kristall (80G - Zauber-Komponente), Gefrorenes Herz (50G - Alchemie)"
    xp: 45
    description: "3m hoher Golem aus massivem Eis. Vom Eismagier erschaffen, befolgt Befehle stur."

  - id: vampir_brut
    name: Vampir-Brut
    type: Untoter
    difficulty: Elite
    size: Mittel
    str: 12
    dex: 14
    con: 10
    int: 10
    wis: 8
    cha: 12
    hp: 40
    armor: 3
    initiative: 7
    movement: 12
    attacks:
      - name: Klauen
        type: Nahkampf
        hit: 9
        damage: 1W6+4
        range: Nahkampf
        special: "2 Angriffe pro Runde"
      - name: Vampirbiss
        type: Nahkampf
        hit: 9
        damage: 2W6+2
        range: Nahkampf
        special: "Heilt Vampir um Schadensmenge. Ziel: Konsti-RW 16 oder -2 max LP (permanent bis Heilzauber)"
    dodge: 7
    skills:
      - "Nahkampf 4"
      - "Schleichen 4"
      - "Täuschung 3"
    abilities:
      - "Vampirismus: Jeder Biss heilt und schwächt Ziel permanent"
      - "Regeneration: +2 LP pro Runde (außer Feuer/Heilig-Schaden)"
      - "Nachtwesen: Perfekte Sicht bei Dunkelheit, +4 auf alle Proben nachts"
      - "Sonnenlicht-Schwäche: 2W6 Schaden/Runde bei direkter Sonne, -4 auf alle Proben"
      - "Charmant: +4 auf Täuschung und Überreden gegen Lebende"
    resistant: [Stich, Stumpf, Kälte]
    weak: [Heilig, Feuer, Sonnenlicht]
    immune: [Gift, Krankheit, Schlaf]
    behavior: "Lauert nachts, charmant bis zum Angriff. Nutzt Geschwindigkeit, mehrere Angriffe. Biss um zu heilen. Flieht vor Sonne."
    loot: "Vampir-Zahn (60G), edle Kleidung (20G), Blutrubin (80G), 1W6+3 Gold"
    xp: 48
    description: "Jungvampir mit blasser Haut, roten Augen, eleganter Kleidung. Diener eines Vampir-Lords."

  - id: hoehlentroll
    name: Höhlentroll
    type: Humanoid
    difficulty: Elite
    size: Riesig
    str: 16
    dex: 6
    con: 16
    int: 3
    wis: 4
    cha: 2
    hp: 60
    armor: 5
    initiative: 3
    movement: 10
    attacks:
      - name: Keule
        type: Nahkampf
        hit: 8
        damage: 3W6+5
        range: Nahkampf
        special: "Bei Krit: Ziel 5m zurückgestoßen"
      - name: Felsbrocken
        type: Fernkampf
        hit: 5
        damage: 2W6+5
        range: 20m
        special: "Bei Treffer: Reflex-RW 14 oder zu Boden geworfen"
    dodge: 3
    skills:
      - "Nahkampf 4"
      - "Fernkampf 2"
    abilities:
      - "Regeneration: +5 LP pro Runde (außer bei Feuer/Säure-Schaden)"
      - "Dicke Haut: Erste 3 Schadenspunkte jeder Attacke werden ignoriert"
      - "Schwacher Geist: -4 gegen mentale Zauber"
      - "Wutanfall: Bei unter 30% HP: +4 Angriff, -2 Verteidigung, doppelte Regeneration"
    resistant: [Kälte, Stumpf]
    weak: [Feuer, Säure]
    immune: []
    behavior: "Territorial, greift Eindringlinge an. Wirft Felsen aus Distanz, dann Nahkampf. Regeneriert schnell, kämpft bis zerstört."
    loot: "Troll-Blut (40G - Heiltränke), Troll-Haut (30G - Rüstung), Keule (5G), 1W6 Silber"
    xp: 52
    description: "3,5m großer grüngrauer Troll mit moosbedeckter Haut. Stinkt, dumm aber regenerativ. Lebt in Höhlen."

  - id: schattenjaeger
    name: Schattenjäger
    type: Dämon
    difficulty: Elite
    size: Mittel
    str: 10
    dex: 16
    con: 10
    int: 12
    wis: 10
    cha: 8
    magic: 8
    hp: 38
    mp: 24
    armor: 4
    initiative: 8
    movement: 12
    attacks:
      - name: Schattenklingen
        type: Nahkampf
        hit: 10
        damage: 2W6+3
        range: Nahkampf
        special: "Ignoriert normale Rüstung, nur magische zählt"
      - name: Schattengriff
        type: Fernkampf
        hit: 10
        damage: 1W6+3
        range: 15m
        special: "Ziel zu Dämon gezogen (5m), Willens-RW 14 oder verängstigt (1 Runde)"
    spells:
      - name: Dunkelheit
        cost: 3 MP
        difficulty: 12
        effect: "Magische Dunkelheit, 10m Radius, 10 Min"
        range: 20m
        special: "Nur Dämon sieht normal darin"
      - name: Schattensprung
        cost: 4 MP
        difficulty: 14
        effect: "Teleport zu Schatten in Sichtweite (30m)"
        range: Selbst
        special: "Freie Aktion"
    dodge: 8
    skills:
      - "Nahkampf 4"
      - "Magie 4 (Schattenmagie 3)"
      - "Schleichen 5"
    abilities:
      - "Dämon: Resistent gegen normale Waffen, schwach gegen Heilig"
      - "Schattengestalt: Kann durch Schatten reisen, +4 auf Schleichen in Dunkelheit"
      - "Unsichtbar in Schatten: In totaler Dunkelheit nicht sichtbar"
      - "Furchtaura: Gegner in 5m: Willens-RW 14 oder -2 auf alle Proben"
    resistant: [Normal-Waffen, Kälte]
    weak: [Heilig, Licht]
    immune: [Angst, Dunkelheit]
    behavior: "Erschafft Dunkelheit, teleportiert sich zu Zielen. Nutzt Furcht und Schatten. Flieht bei hellem Licht."
    loot: "Schattenessenz (70G - Magie), dämonische Klinge (100G), schwarzer Kristall (50G)"
    xp: 50
    description: "Humanoide Schattengestalt mit roten Augen. Beschworen von Dunklen Magiern. Jagt in Dunkelheit."

  # ========================================
  # CHAMPION (Level 6-10)
  # ========================================

  - id: drache_jung
    name: Junger Drache
    type: Bestie
    difficulty: Champion
    size: Riesig
    str: 18
    dex: 10
    con: 16
    int: 12
    wis: 12
    cha: 14
    magic: 10
    hp: 80
    mp: 30
    armor: 10
    initiative: 5
    movement: 12
    attacks:
      - name: Biss
        type: Nahkampf
        hit: 11
        damage: 3W6+6
        range: Nahkampf
        special: "Bei Krit: Ziel geschluckt (1W6 Säureschaden/Runde, STR-RW 18 zum Befreien)"
      - name: Klauen (2x)
        type: Nahkampf
        hit: 11
        damage: 2W6+6
        range: Nahkampf
        special: "Kann beide Klauen in einer Runde nutzen"
      - name: Schwanzschlag
        type: Nahkampf
        hit: 9
        damage: 2W6+8
        range: 3m
        special: "Ziel 10m zurückgeworfen, zu Boden"
    spells:
      - name: Feueratem
        cost: 8 MP
        difficulty: null
        damage: 4W6
        range: Kegel 15m
        special: "Alle in Kegel: Reflex-RW 18 oder voller Schaden (halb bei Erfolg). 1x alle 3 Runden"
    dodge: 5
    skills:
      - "Nahkampf 6"
      - "Magie 5 (Feuermagie 4)"
    abilities:
      - "Drachenangst: Kreaturen unter Level 5 in 30m: Willens-RW 16 oder geflohen (3 Runden)"
      - "Drachenschuppen: Rüstung +10, Feuerimmunität"
      - "Flug: Kann fliegen (Bewegung 20m in der Luft)"
      - "Legendäre Resistenz: 2x pro Tag automatisch RW bestehen"
      - "Mehrfachangriff: Kann Biss + 2 Klauen ODER Schwanzschlag in einer Runde"
    resistant: [Feuer, Normal-Waffen, Stich]
    weak: [Kälte]
    immune: [Feuer, Angst, Schlaf]
    behavior: "Nutzt Feueratem aus Distanz, fliegt. Im Nahkampf: Biss+Klauen. Nutzt Schwanz gegen Mehrere. Intelligent, verhandelt wenn unterlegen."
    loot: "Drachenschuppen (5x 100G), Drachenzahn (150G), Drachenklaue (120G), Drachenhort (2W6x10 Gold + magischer Gegenstand)"
    xp: 100
    description: "8m langer roter Drache, noch nicht ausgewachsen. Intelligent, gierig, arrogant. Baut Hort in Berghöhle."

  - id: lich
    name: Lich
    type: Untoter
    difficulty: Champion
    size: Mittel
    str: 8
    dex: 10
    con: 12
    int: 18
    wis: 16
    cha: 10
    magic: 16
    hp: 70
    mp: 60
    armor: 6
    initiative: 5
    movement: 8
    attacks:
      - name: Todesberührung
        type: Nahkampf
        hit: 9
        damage: 3W6
        range: Nahkampf
        special: "Nekrotischer Schaden, Ziel: Konsti-RW 18 oder max LP -1W6 (permanent bis Großer Heilzauber)"
    spells:
      - name: Feuersturm
        cost: 10 MP
        difficulty: 20
        damage: 2W6+4
        range: 10m Radius, 30m Entfernung
        special: "Alle im Radius, Reflex-RW 18 für halben Schaden"
      - name: Blitzschlag
        cost: 6 MP
        difficulty: 16
        damage: 2W6
        range: 30m
        special: "Betäubt für 1 Runde (Konsti-RW 16)"
      - name: Zeitverlangsamung
        cost: 12 MP
        difficulty: 22
        effect: "Gegner bewegen sich halb so schnell, -4 auf alle Proben"
        range: 10m Radius
        special: "3 Runden, Willens-RW 18 negiert"
      - name: Untote erwecken
        cost: 10 MP
        difficulty: 20
        effect: "Erweckt 1W6 Skelette oder 1W3 Zombies"
        range: 20m
        special: "Braucht Leichen in der Nähe"
    dodge: 5
    skills:
      - "Magie 10 (Nekromantie 8, Evokation 6)"
      - "Gelehrsamkeit 8"
    abilities:
      - "Untot: Immun gegen Gift, Krankheit, Schlaf, Angst"
      - "Phylakterium: Kann nicht permanent getötet werden, regeneriert nach 1W6 Tagen"
      - "Arkanes Genie: +4 auf alle Zauber-Proben"
      - "Legendärer Widerstand: 3x pro Tag automatisch RW bestehen"
      - "Aura des Todes: Lebende in 10m: -2 auf alle Proben"
    resistant: [Kälte, Normal-Waffen, Stich, Stumpf]
    weak: [Heilig, Feuer]
    immune: [Gift, Krankheit, Schlaf, Angst, Gedankenkontrolle]
    behavior: "Bleibt auf Distanz, nutzt mächtige Zauber. Erweckt Untote als Verteidigung. Teleportiert wenn in Gefahr. Verhandelt wenn Phylakterium bedroht."
    loot: "Lich-Phylakterium (unbezahlbar - zerstören!), Nekromanten-Stab (+3 Magie, 500G), Zauberbücher (3x 200G), Runen-Rüstung (+6, 400G), 3W6x10 Gold"
    xp: 120
    description: "Untote Skelett-Magier in zerfetzter Robe. Ehemals mächtiger Magier, jetzt unsterblich durch Phylakterium."

  - id: daemonenprinz
    name: Dämonenprinz
    type: Dämon
    difficulty: Champion
    size: Riesig
    str: 16
    dex: 12
    con: 16
    int: 14
    wis: 10
    cha: 16
    magic: 12
    hp: 85
    mp: 40
    armor: 8
    initiative: 6
    movement: 12
    attacks:
      - name: Flammenschwert
        type: Nahkampf
        hit: 12
        damage: 3W6+5
        range: Nahkampf
        special: "+1W6 Feuerschaden, ignoriert 3 Punkte Rüstung"
      - name: Höllenpeitsche
        type: Nahkampf
        hit: 10
        damage: 2W6+4
        range: 5m
        special: "Zieht Ziel zu Dämon (3m), Schmerz: -2 auf nächste Probe"
    spells:
      - name: Höllenfeuer
        cost: 8 MP
        difficulty: 18
        damage: 3W6+4
        range: Kegel 10m
        special: "Brennt weiter: 1W6/Runde für 3 Runden, Reflex-RW 18"
      - name: Beschwörung (Kleinere Dämonen)
        cost: 10 MP
        difficulty: 20
        effect: "Beschwört 1W3 Schattenbestien"
        range: 10m
        special: "Dienen für 1 Stunde"
      - name: Furchtaura
        cost: 5 MP
        difficulty: 16
        effect: "Alle Gegner in 15m: Willens-RW 18 oder geflohen (3 Runden)"
        range: 15m Radius
        special: null
    dodge: 6
    skills:
      - "Nahkampf 7"
      - "Magie 6 (Feuermagie 5, Dämonenmagie 4)"
    abilities:
      - "Dämon: Resistent gegen normale Waffen, immun gegen Feuer"
      - "Flug: Fliegt mit 15m Bewegung"
      - "Regeneration: +3 LP pro Runde (außer Heilig-Schaden)"
      - "Dämonische Präsenz: Schwächere Kreaturen (Level <4) müssen Willens-RW 16 oder knien nieder"
      - "Legendärer Widerstand: 2x pro Tag automatisch RW bestehen"
    resistant: [Normal-Waffen, Feuer, Kälte, Gift]
    weak: [Heilig]
    immune: [Feuer, Gift, Angst, Krankheit]
    behavior: "Führt von der Luft, nutzt Höllenfeuer. Beschwört Dämonenhelfer. Im Nahkampf: Flammenschwert+Peitsche. Arrogant, verhandelt nicht."
    loot: "Flammenschwert (+3 Schaden, +1W6 Feuer, 800G), Dämonenpanzer (+8, 600G), Dämonenhorn (200G), Höllisches Siegel (400G), 4W6x10 Gold"
    xp: 130
    description: "3,5m großer roter Dämon mit Hörnern, Flügeln, brennenden Augen. General der Hölle, angeführt von Dämonenlord."

  - id: steingolem
    name: Steingolem
    type: Elementar
    difficulty: Champion
    size: Riesig
    str: 20
    dex: 4
    con: 18
    int: 1
    wis: 3
    cha: 1
    hp: 90
    armor: 12
    initiative: 2
    movement: 8
    attacks:
      - name: Steinfaust
        type: Nahkampf
        hit: 10
        damage: 4W6+6
        range: Nahkampf
        special: "Bei Krit: Ziel 10m zurückgeworfen, betäubt (1 Runde)"
      - name: Bodenschlag
        type: Nahkampf
        hit: null
        damage: 2W6+4
        range: 10m Radius um Golem
        special: "Alle in Radius: Reflex-RW 16 oder Schaden + zu Boden. 1x alle 3 Runden"
    dodge: 2
    skills: []
    abilities:
      - "Elementar: Immun gegen Gift, Krankheit, Schlaf, mentale Effekte"
      - "Steinhaut: Rüstung 12, Stich/Stumpf-Waffen halber Schaden"
      - "Unaufhaltsam: Wird nicht müde, ignoriert Gelände"
      - "Magieresistenz: +4 auf alle RW gegen Zauber"
      - "Langsam aber tödlich: Initiative nur 2, aber verfolgt endlos"
    resistant: [Stich, Stumpf, Feuer, Kälte, Blitz, Normal-Waffen]
    weak: [Säure, Erdbeben-Magie]
    immune: [Gift, Krankheit, Schlaf, Gedankenkontrolle, Angst]
    behavior: "Bewacht Ort/Schatz. Greift nächstes Ziel an, nutzt Bodenschlag gegen Gruppen. Folgt Befehlen stur, keine Taktik."
    loot: "Golem-Kern (300G - Magie), Steinbrocken (je 50G - Bau), Magische Runen (200G)"
    xp: 110
    description: "4m hoher Golem aus massivem Stein mit glühenden Runen. Von Magier erschaffen als Wächter."

---

# Suchfunktionen (Dataview-Queries)

## Alle Monster nach Schwierigkeit

```dataview
TABLE name, type, hp, armor, xp
FROM "bestarium"
FLATTEN file.frontmatter.monsters as m
WHERE m.difficulty = "Minion"
SORT m.name ASC
````

## Alle Monster eines Typs

```dataview
TABLE name, difficulty, hp, xp
FROM "bestarium"
FLATTEN file.frontmatter.monsters as m
WHERE m.type = "Bestie"
SORT m.difficulty ASC, m.name ASC
```

## Monster mit Magie

```dataview
TABLE name, type, difficulty, mp, spells
FROM "bestarium"
FLATTEN file.frontmatter.monsters as m
WHERE m.magic != null AND m.magic > 0
SORT m.difficulty ASC
```

## Monster nach Level-Bereich

### Level 1-3 (Minions)

```dataview
TABLE name, type, hp, xp
FROM "bestarium"
FLATTEN file.frontmatter.monsters as m
WHERE m.difficulty = "Minion"
```

### Level 2-5 (Standard)

```dataview
TABLE name, type, hp, xp
FROM "bestarium"
FLATTEN file.frontmatter.monsters as m
WHERE m.difficulty = "Standard"
```

### Level 4-7 (Elite)

```dataview
TABLE name, type, hp, xp
FROM "bestarium"
FLATTEN file.frontmatter.monsters as m
WHERE m.difficulty = "Elite"
```

### Level 6-10 (Champion)

```dataview
TABLE name, type, hp, xp
FROM "bestarium"
FLATTEN file.frontmatter.monsters as m
WHERE m.difficulty = "Champion"
```

## Monster nach Resistenzen/Schwächen

```dataview
TABLE name, difficulty, resistant, weak
FROM "bestarium"
FLATTEN file.frontmatter.monsters as m
WHERE contains(m.weak, "Feuer")
```

## Untote Monster

```dataview
TABLE name, difficulty, hp, abilities
FROM "bestarium"
FLATTEN file.frontmatter.monsters as m
WHERE m.type = "Untoter"
SORT m.difficulty ASC
```

---

# Monster-Übersicht (Schnellreferenz)

|ID|Name|Typ|Schwierigkeit|HP|XP|
|---|---|---|---|---|---|
|waldwolf|Waldwolf|Bestie|Minion|12|5|
|riesige_ratte|Riesige Ratte|Bestie|Minion|8|3|
|goblin|Goblin|Humanoid|Minion|10|5|
|skelett_krieger|Skelett-Krieger|Untoter|Minion|14|6|
|riesige_spinne|Riesige Spinne|Bestie|Minion|11|6|
|ork_krieger|Ork-Krieger|Humanoid|Standard|25|15|
|bandit|Bandit|Humanoid|Standard|18|12|
|zombie|Zombie|Untoter|Standard|22|14|
|ork_schamane|Ork-Schamane|Humanoid|Standard|22|20|
|ghul|Ghul|Untoter|Standard|20|16|
|werwolf|Werwolf|Bestie|Elite|45|40|
|ork_haeuptling|Ork-Häuptling|Humanoid|Elite|55|50|
|eisgolem|Eisgolem|Elementar|Elite|50|45|
|vampir_brut|Vampir-Brut|Untoter|Elite|40|48|
|hoehlentroll|Höhlentroll|Humanoid|Elite|60|52|
|schattenjaeger|Schattenjäger|Dämon|Elite|38|50|
|drache_jung|Junger Drache|Bestie|Champion|80|100|
|lich|Lich|Untoter|Champion|70|120|
|daemonenprinz|Dämonenprinz|Dämon|Champion|85|130|
|steingolem|Steingolem|Elementar|Champion|90|110|

---

# Hinweise zur Nutzung

## In Obsidian verwenden

1. **Dataview-Plugin installieren** (falls noch nicht vorhanden)
2. **Diese Datei als `bestarium.md` speichern**
3. **Queries in andere Notizen einbinden**

## Neue Monster hinzufügen

Einfach neue Monster im YAML-Block ergänzen:

```yaml
  - id: neues_monster
    name: Neues Monster
    type: Bestie
    difficulty: Standard
    # ... restliche Felder
```

## Kategorien erstellen

Erstelle separate Markdown-Dateien für Kategorien:

**`/Bestien/uebersicht.md`:**

```dataview
TABLE name, difficulty, hp, xp
FROM "bestarium"
FLATTEN file.frontmatter.monsters as m
WHERE m.type = "Bestie"
```

---

# Noch zu ergänzen

- Boss-Monster (Level 8+)
    
- Legendäre Monster (Level 12+)
    
- Regionale Varianten (Wüsten-Wolf, Eis-Goblin, etc.)
    
- Tiermenschen-Stämme als Gegner
    
- Shaper-Kreaturen
    
- Meer-Kreaturen
    
- Flugkreaturen
    
- Pflanzen-Monster
    
- Magische Konstrukte
    
    # ========================================
    
    # BOSS (Level 8+)
    
    # ========================================
    
    - id: vampir_lord name: Vampir-Lord Valdis type: Untoter difficulty: Boss size: Mittel str: 14 dex: 16 con: 14 int: 16 wis: 14 cha: 18 magic: 14 hp: 120 mp: 50 armor: 6 initiative: 8 movement: 14 attacks:
        
        - name: Vampirklauen type: Nahkampf hit: 12 damage: 2W6+5 range: Nahkampf special: "3 Angriffe pro Runde möglich"
        - name: Vampirbiss type: Nahkampf hit: 12 damage: 3W6+4 range: Nahkampf special: "Heilt Valdis um Schadensmenge. Ziel: Konsti-RW 18 oder -1W6 max LP permanent + mögliche Vampirisierung"
        - name: Blutklinge type: Nahkampf hit: 13 damage: 3W6+6 range: Nahkampf special: "+2W6 gegen geschwächte Ziele (unter 50% HP)" spells:
        - name: Gedankenkontrolle cost: 8 MP difficulty: 18 effect: "Ziel folgt 1 Befehl (nicht selbstmörderisch)" range: 15m special: "Willens-RW 18, hält 1 Stunde"
        - name: Nebelgestalt cost: 6 MP difficulty: 16 effect: "Wird zu Nebel, immun gegen physischen Schaden" range: Selbst special: "Bewegung 20m, hält 3 Runden"
        - name: Blutsturm cost: 12 MP difficulty: 20 damage: 2W6+6 range: 15m Radius special: "Alle Lebenden nehmen Schaden, Valdis heilt um Hälfte"
        - name: Vampir-Brut beschwören cost: 15 MP difficulty: 22 effect: "Beschwört 1W3 Vampir-Brut" range: 10m special: "Dienen bis zerstört" dodge: 8 skills:
        - "Nahkampf 8"
        - "Magie 8 (Nekromantie 6, Gedankenmagie 5)"
        - "Täuschung 7"
        - "Einschüchtern 6" abilities:
        - "Vampir-Lord: Regeneration +5 LP/Runde (außer Feuer/Heilig)"
        - "Mehrfachangriff: 3 Klauen-Angriffe ODER 2 Klauen + Biss ODER Blutklinge + Zauber"
        - "Uralter Vampir: Immun gegen Schlaf, Angst, Gedankenkontrolle, normale Waffen"
        - "Legendäre Aktionen: 3 pro Runde (außerhalb eigener Runde nutzbar)"
        - "Charmant: +6 auf Täuschung/Überreden gegen Lebende, Ziel Willens-RW 16"
        - "Blutbindung: Kann getrunkenes Blut nutzen um Ziel zu orten (100km Reichweite)"
        - "Schattenreise: Kann als Aktion zu beliebigem Schatten teleportieren (Sichtweite)"
        - "Nekromantische Meisterschaft: Kann Tote als Diener erwecken (1 Aktion, kostet 5 MP)" resistant: [Normal-Waffen, Stich, Stumpf, Kälte, Blitz] weak: [Heilig, Feuer, Sonnenlicht] immune: [Gift, Krankheit, Schlaf, Angst, Gedankenkontrolle] behavior: "Charmant und höflich bis zum Kampf. Nutzt Gedankenkontrolle auf Schwächsten. Beschwört Vampir-Brut als Verteidigung. Mehrfachangriffe gegen stärksten Gegner. Bei unter 40 HP: Nebelgestalt zur Flucht oder Blutsturm zur Heilung. Flieht wenn bedroht, kehrt später zurück." loot: "Blutklinge (+4 Schaden, heilt bei Tod, 1200G), Vampir-Robe (+6 Rüstung, +2 CHA, 800G), Blutrubin-Ring (regeneriert 2 MP/Runde, 600G), Nekromanten-Grimoire (Zauberbuch, 500G), 5W6x10 Gold, Kunstwerke (2W6x100 G)" xp: 200 description: "Valdis ist ein 400 Jahre alter Vampir-Lord. Elegant in schwarzer Adelskleidung, blasse Haut, lange schwarze Haare, durchdringende rote Augen. Herrscher über Vampir-Clan mit 20+ Brut-Vampiren. Bewohnt verfallenes Schloss in den Bergen. Kultiviert, aber absolut rücksichtslos."
    - id: ork_kriegsfuerst name: Ork-Kriegsfürst Grokmash der Schädelbrecher type: Humanoid difficulty: Boss size: Riesig str: 18 dex: 10 con: 16 int: 8 wis: 8 cha: 12 hp: 140 armor: 8 initiative: 5 movement: 12 attacks:
        
        - name: Legendäre Zweihandaxt "Weltenspalter" type: Nahkampf hit: 14 damage: 4W6+8 range: Nahkampf special: "Bei Krit: Spaltet Rüstung, Rüstungswert -2 permanent"
        - name: Schildstoß type: Nahkampf hit: 12 damage: 2W6+6 range: Nahkampf special: "Ziel 10m zurückgestoßen, betäubt (1 Runde, Konsti-RW 16)"
        - name: Wirbelwind type: Nahkampf hit: 14 damage: 3W6+8 range: 5m Radius special: "Trifft alle Gegner in Reichweite. 1x alle 3 Runden" spells:
        - name: Schlachtruf cost: null difficulty: null effect: "Alle Orks +4 Angriff, +2 Schaden (5 Runden). Gegner Willens-RW 18 oder -4 alle Proben (3 Runden)" range: 30m Radius special: "1x pro Kampf, freie Aktion zu Kampfbeginn" dodge: 5 skills:
        - "Nahkampf 10 (Zweihandwaffen 8, Schilde 6)"
        - "Einschüchtern 8"
        - "Taktik 5" abilities:
        - "Kriegsfürst: +4 Angriff/Verteidigung wenn Orks in Sicht"
        - "Mehrfachangriff: 2 Axt-Angriffe + Schildstoß ODER Wirbelwind"
        - "Berserker-Wut der Legende: Bei unter 50 HP: +6 Angriff, +2W6 Schaden, -3 Verteidigung, Immunität gegen Schmerz"
        - "Legendäre Aktionen: 3 pro Runde"
        - "Unaufhaltsam: Immun gegen Umwerfen, Zurückstoßen, Furcht"
        - "Ork-Armee: Kann 2W6 Ork-Krieger als Verstärkung rufen (1x pro Kampf, dauert 2 Runden)"
        - "Legendäre Zähigkeit: Bei 0 LP: 3x RW 16, bei Erfolg bleibt bei 1 LP" resistant: [Gift, Angst, Blitz, Normal-Waffen unter +2] weak: [Heilig] immune: [Einschüchtern, Angst] behavior: "Nutzt Schlachtruf zu Beginn. Stürmt auf stärksten Gegner, nutzt Mehrfachangriffe. Bei Gegnern in Gruppe: Wirbelwind. Ruft Verstärkung wenn bedrängt. Bei Berserker-Wut: Rücksichtslos brutal. Kämpft bis zum Tod, keine Flucht." loot: "Weltenspalter (+6 Schaden, spaltet Rüstung, 2000G), Kriegsfürsten-Panzer (+8 Rüstung, 1200G), Schädelbrecher-Schild (+3 Rüstung, Schildstoß +1W6, 800G), Kriegsbanner (inspiriert Orks, 400G), Kriegshorn (ruft Verstärkung, 300G), 8W6x10 Gold" xp: 250 description: "Grokmash ist ein 2,8m großer Ork-Kriegsfürst. Dunkelgrüne, vernarbte Haut bedeckt von Kriegsbemalung und Trophäen. Trägt massiven Plattenpanzer aus eroberten Rüstungen. Führt Armee von 200+ Orks. Legendärer Krieger, hat 47 Duelle gegen Champions gewonnen. Respektiert nur Stärke."
    - id: erzdaemon name: Erzdämon Mal'kazar der Zerstörer type: Dämon difficulty: Boss size: Riesig str: 20 dex: 14 con: 18 int: 16 wis: 12 cha: 18 magic: 16 hp: 150 mp: 80 armor: 10 initiative: 7 movement: 14 attacks:
        
        - name: Höllenklingen (Zweihandwaffe) type: Nahkampf hit: 15 damage: 4W6+8 range: Nahkampf special: "+2W6 Feuerschaden, kann 2x pro Runde angreifen"
        - name: Schwanzstachel type: Nahkampf hit: 13 damage: 3W6+6 range: 5m special: "Gift: Konsti-RW 18 oder 2W6 Schaden/Runde für 4 Runden"
        - name: Flammenatem type: Fernkampf hit: null damage: 5W6 range: Kegel 20m special: "Alle in Kegel: Reflex-RW 18 oder voller Schaden (halb bei Erfolg). 1x alle 3 Runden" spells:
        - name: Höllentor öffnen cost: 20 MP difficulty: 24 effect: "Beschwört 2W6 Kleinere Dämonen oder 1W3 Dämonenprinzen" range: 15m special: "Dienen bis zerstört oder 1 Stunde"
        - name: Dämonisches Inferno cost: 15 MP difficulty: 22 damage: 4W6+6 range: 20m Radius special: "Alle Nicht-Dämonen, brennt weiter (2W6/Runde, 3 Runden)"
        - name: Seelen bannen cost: 12 MP difficulty: 20 effect: "Ziel paralysiert, Seele eingesperrt" range: 20m special: "Willens-RW 20, hält bis Dispel oder Tod des Dämons"
        - name: Teleportation cost: 8 MP difficulty: 16 effect: "Teleportiert bis zu 60m" range: Selbst special: "Freie Aktion" dodge: 7 skills:
        - "Nahkampf 10"
        - "Magie 10 (Feuermagie 8, Dämonenmagie 8)"
        - "Einschüchtern 9" abilities:
        - "Erzdämon: Regeneration +8 LP/Runde (außer Heilig)"
        - "Mehrfachangriff: 2 Klingen-Angriffe + Schwanzstachel ODER Flammenatem + Zauber"
        - "Legendäre Aktionen: 4 pro Runde"
        - "Dämonenlord-Aura: Alle Nicht-Dämonen in 20m: -4 auf alle Proben, müssen Willens-RW 18 oder verängstigt"
        - "Flug: Fliegt mit 20m Bewegung"
        - "Unsterblich (in Hölle): Wenn getötet, regeneriert in Hölle nach 1W6 Wochen"
        - "Seelenfresser: Für jeden getöteten Gegner: +10 temporäre HP"
        - "Feuerimmunität: Immun gegen Feuer, heilt durch Feuerschaden" resistant: [Normal-Waffen, Feuer, Kälte, Blitz, Gift, Säure] weak: [Heilig] immune: [Feuer, Gift, Krankheit, Angst, Gedankenkontrolle, Schlaf] behavior: "Erscheint in Flammenexplosion. Nutzt Dämonenaura zur Einschüchterung. Öffnet Höllentor für Verstärkung. Nutzt Teleportation für taktische Positionierung. Flammenatem gegen Gruppen. Mehrfachangriffe gegen Einzelne. Bei unter 50 HP: Inferno + Seelen bannen. Kämpft bis zum Tod, kehrt aus Hölle zurück." loot: "Höllenklingen (+8 Schaden, +2W6 Feuer, 3000G), Dämonenpanzer (+10 Rüstung, Feuerimmunität, 2500G), Seelenedelstein (speichert Seelen, unbezahlbar), Höllenherzfragment (1500G - Ritual-Komponente), Dämonisches Siegel (2000G - Beschwörung), 10W6x10 Gold" xp: 300 description: "Mal'kazar ist ein 4m großer Erzdämon. Roter, gehörnter Körper mit Lavanarben. Flammen lodern um ihn. Sechs Augen brennen höllisch gelb. Riesige Fledermausflügel. General der Höllenarmeen. Wurde vor 1000 Jahren gebannt, kürzlich freigesetzt. Plant Invasion von Terranea."
    - id: drache_erwachsen name: Erwachsener Drache - Infernus der Unsterbliche Flamme type: Bestie difficulty: Boss size: Gigantisch str: 22 dex: 12 con: 20 int: 16 wis: 16 cha: 18 magic: 18 hp: 180 mp: 70 armor: 14 initiative: 6 movement: 15 attacks:
        
        - name: Biss type: Nahkampf hit: 16 damage: 5W6+10 range: Nahkampf special: "Bei Krit: Ziel verschluckt (3W6 Feuerschaden/Runde, STR-RW 20 zum Befreien)"
        - name: Klauen (2x) type: Nahkampf hit: 16 damage: 3W6+10 range: Nahkampf special: "Kann beide Klauen in einer Runde nutzen"
        - name: Schwanzschlag type: Nahkampf hit: 14 damage: 4W6+12 range: 5m special: "Trifft alle in Linie, 15m zurückgeworfen"
        - name: Flügelsturm type: Nahkampf hit: null damage: 2W6+8 range: 10m Radius special: "Alle am Boden: Reflex-RW 18 oder zurückgeworfen + zu Boden" spells:
        - name: Inferno-Atem cost: 15 MP difficulty: null damage: 8W6 range: Kegel 30m special: "Reflex-RW 20 für halben Schaden, brennt weiter (3W6/Runde, 3 Runden). Nutzbar alle 3 Runden"
        - name: Meteor-Regen cost: 20 MP difficulty: 24 damage: 4W6+8 range: 30m Radius, 50m Entfernung special: "6 Meteore fallen, jeder trifft 5m Radius (Reflex-RW 18)"
        - name: Drachenfurcht cost: 10 MP difficulty: 20 effect: "Alle unter Level 8 in 50m: geflohen (5 Runden)" range: 50m Radius special: "Willens-RW 20, 1x pro Kampf"
        - name: Feuer-Immunität teilen cost: 5 MP difficulty: 14 effect: "Verbündeter immun gegen Feuer (10 Min)" range: Berührung special: null dodge: 6 skills:
        - "Nahkampf 12"
        - "Magie 12 (Feuermagie 10, Evokation 8)"
        - "Einschüchtern 10"
        - "Gelehrsamkeit 8" abilities:
        - "Uralter Drache: +12 auf alle mentalen RW, spricht 8 Sprachen"
        - "Mehrfachangriff: Biss + 2 Klauen + Schwanzschlag ODER Flügelsturm + Zauber"
        - "Legendäre Aktionen: 4 pro Runde"
        - "Drachenpanzer: Rüstung 14, normale Waffen halber Schaden"
        - "Legendäre Resistenz: 4x pro Tag automatisch RW bestehen"
        - "Flug: Fliegt mit 25m Bewegung"
        - "Hortbindung: Kann zu seinem Hort teleportieren (1x pro Tag, bis 100km)"
        - "Feuerbeherrschung: Immun gegen Feuer, kann Feuer kontrollieren (30m Radius)"
        - "Furchteinflößend: Automatische Furcht-Aura (30m, Willens-RW 18 zu Beginn)" resistant: [Normal-Waffen, Stich, Stumpf, Blitz] weak: [Kälte, Drachenwaffen] immune: [Feuer, Angst, Schlaf, Gedankenkontrolle] behavior: "Nutzt Drachenfurcht zu Beginn. Fliegt hoch, nutzt Inferno-Atem und Meteor-Regen. Landet für Mehrfachangriffe gegen gefährlichste Gegner. Bei unter 60 HP: Inferno-Atem + Flügelsturm, dann Flucht in die Luft. Verhandelt wenn ernsthaft bedroht - Drachen sind nicht dumm." loot: "Drachenhort (50W6x10 Gold + 3W6 magische Gegenstände), Drachenschuppen (20x 200G), Drachenzähne (10x 300G), Drachenherz (3000G - mächtigstes Alchemie-Material), Flammenjuwel (2500G - Feuermagie +4), Drachenkrone (4000G - Legendär)" xp: 400 description: "Infernus ist ein 800 Jahre alter roter Drache, 15m lang mit 30m Flügelspannweite. Schuppen glühen wie Lava. Atmet Feuer das Stein schmilzt. Hochintelligent, arrogant, gierig. Herrscht über Berge, terrorisiert umliegende Königreiche. Sammelt magische Artefakte und Gold seit Jahrhunderten."
    - id: nekromanten_fuerst name: Nekromanten-Fürst Mordakai der Ewige type: Humanoid difficulty: Boss size: Mittel str: 10 dex: 12 con: 14 int: 20 wis: 18 cha: 14 magic: 20 hp: 100 mp: 100 armor: 8 initiative: 6 movement: 10 attacks:
        
        - name: Nekromantenstab der Seelen type: Nahkampf hit: 11 damage: 2W6+4 range: Nahkampf special: "+2W6 nekrotischer Schaden, absorbiert Seele bei Tod (heilt Mordakai um 2W6)"
        - name: Todesberührung type: Nahkampf hit: 11 damage: 4W6 range: Nahkampf special: "Nekrotisch, Konsti-RW 20 oder max LP -2W6 permanent" spells:
        - name: Armee der Toten cost: 25 MP difficulty: 24 effect: "Erweckt 3W6 Untote (Skelette/Zombies/Ghule)" range: 30m special: "Dienen bis zerstört"
        - name: Todeswoge cost: 18 MP difficulty: 22 damage: 5W6 range: Kegel 20m special: "Nekrotisch, Konsti-RW 18 oder max LP -1W6. Getötete werden zu Zombies"
        - name: Seelenkäfig cost: 15 MP difficulty: 20 effect: "Ziel paralysiert, Seele gefangen" range: 25m special: "Willens-RW 20, kann Seele extrahieren nach 3 Runden"
        - name: Lebensraub cost: 12 MP difficulty: 18 damage: 3W6 range: 30m special: "Heilt Mordakai um halben Schaden"
        - name: Todesrüstung cost: 10 MP difficulty: 16 effect: "+6 Rüstung, reflektiert 1W6 nekrotischen Schaden" range: Selbst special: "10 Minuten"
        - name: Teleportation cost: 8 MP difficulty: 14 effect: "Teleportiert bis 40m" range: Selbst special: "Freie Aktion" dodge: 6 skills:
        - "Magie 15 (Nekromantie 12, Evokation 8)"
        - "Gelehrsamkeit 12"
        - "Einschüchtern 8" abilities:
        - "Meister-Nekromant: Alle nekromantischen Zauber kosten -4 MP"
        - "Legendäre Aktionen: 4 pro Runde (kann Zauber außerhalb seiner Runde wirken)"
        - "Seelenspeicher: Speichert 10 Seelen, kann jede als Aktion opfern um 3W6 LP zu heilen"
        - "Untoten-Armee: Beginnt Kampf mit 2W6 bereits erweckten Untoten"
        - "Phylakterium: Kann nicht permanent getötet werden, regeneriert nach 1W6+2 Tagen"
        - "Nekromantische Aura: Untote in 30m: +2 auf alle Proben, Lebende: -2 auf alle Proben"
        - "Gedankenlesend: +4 auf Verteidigung, kann Gedanken in 20m lesen"
        - "Legendäre Resistenz: 4x pro Tag automatisch RW bestehen" resistant: [Kälte, Blitz, Normal-Waffen, Nekrotisch] weak: [Heilig, Feuer] immune: [Gift, Krankheit, Schlaf, Angst, Nekrotisch] behavior: "Nutzt Untoten-Armee als Schutz. Wirkt Todesrüstung zu Beginn. Bleibt auf Distanz, nutzt Todeswoge und Lebensraub. Erweckt gefallene Gegner mit Armee der Toten. Bei Bedrohung: Seelenkäfig auf Stärksten, dann Teleportation. Opfert Seelen zur Heilung. Kämpft strategisch, flieht wenn Phylakterium bedroht." loot: "Nekromantenstab (+6 Magie, absorbiert Seelen, 3500G), Todesrobe (+8 Rüstung, +4 Nekromantie, 2000G), Seelenedelstein (enthält 10 Seelen, unbezahlbar), Phylakterium (MUSS zerstört werden!), Nekromantie-Grimoire (alle Nekromantie-Zauber, 2500G), Totenmaske (1200G), 12W6x10 Gold" xp: 350 description: "Mordakai ist ein 600 Jahre alter Nekromant, verwandelt in Lich. Skelettartig mit glühenden grünen Augen. Trägt schwarze Roben mit Runen. Beherrscht Untoten-Legion von 1000+ Kreaturen. Plant, alle Lebenden in Untote zu verwandeln. Genial, geduldig, absolut böse."