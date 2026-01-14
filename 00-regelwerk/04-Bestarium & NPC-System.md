
---
## 📋 Template-System

### Grundprinzip

Jedes Monster/NPC wird nach folgendem Schema erstellt:

1. **Grundwerte** (LP, Attribute, Rüstung)
2. **Kampfwerte** (Angriffe, Schaden, Verteidigung)
3. **Fähigkeiten & Spezialisierungen**
4. **Besondere Eigenschaften**
5. **Beute & Belohnungen**

---

## 🎲 Schwierigkeitsgrade

Monster und NPCs werden in **Schwierigkeitsgrade** eingeteilt:

|**Grad**|**Beschreibung**|**Empfohlenes Spieler-Level**|**LP-Bereich**|
|---|---|---|---|
|**Minion**|Schwache Gegner, schnell besiegt|1-3|5-15 LP|
|**Standard**|Durchschnittliche Gegner|2-5|15-30 LP|
|**Elite**|Starke Einzelgegner|4-7|30-60 LP|
|**Champion**|Sehr gefährlich, Boss-Vorstufe|6-10|60-100 LP|
|**Boss**|Kampagnen-Boss, extrem gefährlich|8+|100-200 LP|
|**Legendär**|Weltbedrohung, Drachen, Götter|12+|200+ LP|

---

## 📝 Monster-Template (Blank)

```markdown
# [Monster-Name]

**Typ**: [Bestie/Untoter/Dämon/Elementar/Humanoid/etc.]
**Schwierigkeitsgrad**: [Minion/Standard/Elite/Champion/Boss/Legendär]
**Größe**: [Klein/Mittel/Groß/Riesig]

---

## Attribute

- **Stärke**: ___ (Bonus: ___)
- **Geschicklichkeit**: ___ (Bonus: ___)
- **Konstitution**: ___ (Bonus: ___)
- **Intelligenz**: ___ (Bonus: ___)
- **Weisheit**: ___ (Bonus: ___)
- **Charisma**: ___ (Bonus: ___)

---

## Kampfwerte

- **Lebenspunkte (LP)**: ___
- **Rüstungswert**: ___
- **Initiative**: ___ (Geschicklichkeit-Bonus)
- **Bewegungsreichweite**: ___ Meter

---

## Angriffe

### [Angriff 1 - Name]
- **Typ**: [Nahkampf/Fernkampf/Magie]
- **Trefferprobe**: 2W6 + ___ (Attribut-Bonus + Fähigkeit)
- **Schaden**: ___W6 + ___
- **Reichweite**: ___ Meter
- **Besonderheiten**: ___

### [Angriff 2 - Name]
- **Typ**: [Nahkampf/Fernkampf/Magie]
- **Trefferprobe**: 2W6 + ___ (Attribut-Bonus + Fähigkeit)
- **Schaden**: ___W6 + ___
- **Reichweite**: ___ Meter
- **Besonderheiten**: ___

---

## Verteidigung

- **Ausweichen**: 2W6 + ___ (Geschicklichkeit-Bonus + Fähigkeit)
- **Natürliche Rüstung**: ___ (bereits in Rüstungswert eingerechnet)

---

## Fähigkeiten & Eigenschaften

- **[Fähigkeit 1]**: Beschreibung
- **[Fähigkeit 2]**: Beschreibung
- **[Besondere Eigenschaft]**: Beschreibung

---

## Resistenzen & Schwächen

- **Resistent gegen**: [Feuer/Kälte/Gift/Physisch/Magie]
- **Schwach gegen**: [Feuer/Kälte/Gift/Physisch/Magie/Heilig]
- **Immun gegen**: [Angst/Schlaf/Betäubung/Krankheit]

---

## Verhalten & Taktik

**Kampfstil**: ___
**Intelligenz**: ___
**Sozialverhalten**: ___

---

## Beute & Belohnungen

- **Loot**: ___
- **Erfahrung**: ___ XP
- **Besondere Drops**: ___

---

## Beschreibung

[Aussehen, Lebensraum, Verhalten, Hintergrund]

```

---

## 🐺 Beispiel-Monster: Waldwolf

```markdown
# Waldwolf

**Typ**: Bestie
**Schwierigkeitsgrad**: Minion
**Größe**: Mittel

---

## Attribute

- **Stärke**: 8 (Bonus: 4)
- **Geschicklichkeit**: 10 (Bonus: 5)
- **Konstitution**: 6 (Bonus: 3)
- **Intelligenz**: 2 (Bonus: 1)
- **Weisheit**: 6 (Bonus: 3)
- **Charisma**: 4 (Bonus: 2)

---

## Kampfwerte

- **Lebenspunkte (LP)**: 12
- **Rüstungswert**: 2 (dickes Fell)
- **Initiative**: 5
- **Bewegungsreichweite**: 12 Meter

---

## Angriffe

### Biss
- **Typ**: Nahkampf
- **Trefferprobe**: 2W6 + 4 (Stärke-Bonus)
- **Schaden**: 1W6 + 2
- **Reichweite**: Nahkampf
- **Besonderheiten**: Bei kritischem Erfolg (12) greift der Wolf an und reißt das Ziel zu Boden (Stärke-Probe Schwierigkeit 14 zum Aufstehen)

### Sprung-Angriff
- **Typ**: Nahkampf
- **Trefferprobe**: 2W6 + 5 (Geschicklichkeit-Bonus)
- **Schaden**: 1W6 + 1
- **Reichweite**: 5 Meter Sprung
- **Besonderheiten**: Überraschungsangriff, +2 auf Trefferprobe wenn Ziel nicht aufmerksam ist

---

## Verteidigung

- **Ausweichen**: 2W6 + 5
- **Natürliche Rüstung**: +2 (dickes Fell)

---

## Fähigkeiten & Eigenschaften

- **Rudeltaktik**: +2 auf Angriffe für jeden weiteren Wolf in Nahkampfreichweite (max. +6)
- **Nachtjäger**: Keine Abzüge bei Dunkelheit
- **Fährtenlesen**: Kann Beute über große Distanzen verfolgen

---

## Resistenzen & Schwächen

- **Resistent gegen**: Kälte
- **Schwach gegen**: Feuer (-2 Rüstung gegen Feuerschaden)
- **Immun gegen**: -

---

## Verhalten & Taktik

**Kampfstil**: Wölfe greifen im Rudel an, umzingeln Gegner und nutzen ihre Geschwindigkeit
**Intelligenz**: Geringe tierische Intelligenz, aber ausgeprägte Jagdinstinkte
**Sozialverhalten**: Rudeltiere, beschützen einander

---

## Beute & Belohnungen

- **Loot**: Wolfsfell (5 S), Wolfszähne (2 S)
- **Erfahrung**: 5 XP pro Wolf
- **Besondere Drops**: -

---

## Beschreibung

Waldwölfe sind die häufigsten Raubtiere in den Wäldern von Terranea. Mit grauem bis braunem Fell, scharfen Zähnen und gelben Augen sind sie perfekte Jäger. Sie leben in Rudeln von 4-8 Tieren und jagen koordiniert. Obwohl sie Menschen normalerweise meiden, werden hungrige Wölfe im Winter aggressiv.

```

---

## 👹 Beispiel-Monster: Ork-Krieger

```markdown
# Ork-Krieger

**Typ**: Humanoid
**Schwierigkeitsgrad**: Standard
**Größe**: Groß

---

## Attribute

- **Stärke**: 12 (Bonus: 6)
- **Geschicklichkeit**: 6 (Bonus: 3)
- **Konstitution**: 10 (Bonus: 5)
- **Intelligenz**: 4 (Bonus: 2)
- **Weisheit**: 4 (Bonus: 2)
- **Charisma**: 3 (Bonus: 2)

---

## Kampfwerte

- **Lebenspunkte (LP)**: 25
- **Rüstungswert**: 4 (Lederrüstung + Schild)
- **Initiative**: 3
- **Bewegungsreichweite**: 8 Meter

---

## Angriffe

### Großaxt
- **Typ**: Nahkampf
- **Trefferprobe**: 2W6 + 6 (Stärke-Bonus) + 3 (Nahkampf-Fähigkeit) = 2W6 + 9
- **Schaden**: 2W6 + 4
- **Reichweite**: Nahkampf
- **Besonderheiten**: Kann mit voller Kraft zuschlagen (Malus -2 auf Treffer, aber +1W6 Schaden)

### Wurfspeer
- **Typ**: Fernkampf
- **Trefferprobe**: 2W6 + 3 (Geschicklichkeit-Bonus) + 2 (Fernkampf-Fähigkeit) = 2W6 + 5
- **Schaden**: 1W6 + 4
- **Reichweite**: 15 Meter
- **Besonderheiten**: Nur 1-2 Speere pro Ork

---

## Verteidigung

- **Ausweichen**: 2W6 + 3
- **Schildblock**: 2W6 + 6 (bei Schild-Nutzung, +2 Rüstung)
- **Natürliche Zähigkeit**: Reduziert ersten erlittenen Schaden pro Kampf um 3 Punkte

---

## Fähigkeiten & Eigenschaften

- **Nahkampf**: 3
- **Fernkampf**: 2
- **Wutanfall**: Bei unter 10 LP: +2 auf alle Angriffe, aber -2 auf Verteidigung
- **Schmerzresistenz**: Ignoriert Abzüge durch Verletzungen bis LP auf 5 fallen
- **Ork-Stärke**: Kann schwere Waffen ohne Abzug führen

---

## Resistenzen & Schwächen

- **Resistent gegen**: Gift (+4 auf Rettungswürfe gegen Gift)
- **Schwach gegen**: Heilige Magie (doppelter Schaden von heiligen Zaubern)
- **Immun gegen**: -

---

## Verhalten & Taktik

**Kampfstil**: Aggressiv und direkt, stürmt auf Gegner zu, nutzt rohe Kraft
**Intelligenz**: Niedrig, aber kann einfache Befehle befolgen
**Sozialverhalten**: Folgen dem Stärksten, respektieren nur Macht

---

## Beute & Belohnungen

- **Loot**: 
  - Großaxt (4 G)
  - Lederrüstung (5 G)
  - Schild (1 G)
  - 1W6 Silbermünzen
- **Erfahrung**: 15 XP
- **Besondere Drops**: Ork-Zahn-Halskette (5 S, Trophäe)

---

## Beschreibung

Ork-Krieger sind die Frontkämpfer der Ork-Armeen. Mit grüner, narbiger Haut, muskulösen Körpern und Hauern sind sie furchterregende Gegner. Sie tragen einfache Lederrüstungen und bevorzugen große, schwere Waffen. Ihre Kampftaktik ist simpel: Angriff mit roher Gewalt. Sie leben für den Kampf und sterben selten im Bett.

**Lebensraum**: Ork-Lager, Grenzgebiete von Sunar, Schlachtfelder
**Häufigkeit**: Sehr häufig an der Front

```

---

## 🧙 NPC-Template (Blank)

```markdown
# [NPC-Name]

**Rasse**: [Terraner/Sylvaner/Khazad/Tiermensch/Shaper]
**Beruf/Rolle**: [Händler/Wache/Magier/Priester/Adliger/etc.]
**Alter**: ___
**Geschlecht**: ___

---

## Persönlichkeit

**Charakterzüge**: ___
**Motivation**: ___
**Ängste/Schwächen**: ___
**Besonderheiten**: ___

---

## Aussehen

**Größe**: ___
**Statur**: ___
**Haare**: ___
**Augen**: ___
**Kleidung**: ___
**Besondere Merkmale**: ___

---

## Attribute (Optional für Kampf-NPCs)

- **Stärke**: ___ (Bonus: ___)
- **Geschicklichkeit**: ___ (Bonus: ___)
- **Konstitution**: ___ (Bonus: ___)
- **Intelligenz**: ___ (Bonus: ___)
- **Weisheit**: ___ (Bonus: ___)
- **Charisma**: ___ (Bonus: ___)

---

## Fähigkeiten

- **[Hauptfähigkeit 1]**: Stufe ___
- **[Hauptfähigkeit 2]**: Stufe ___
- **[Spezialisierung]**: Stufe ___

---

## Beziehungen

- **Familie**: ___
- **Freunde**: ___
- **Feinde**: ___
- **Organisation**: ___

---

## Hintergrund

[Geschichte des NPCs, wichtige Ereignisse, warum ist er hier?]

---

## Quest-Potential

**Mögliche Quests**:
- ___
- ___

**Belohnungen**:
- ___

---

## Handelswaren (falls Händler)

| **Item** | **Preis** | **Verfügbarkeit** |
|----------|-----------|-------------------|
|          |           |                   |

---

## Dialog-Beispiele

**Begrüßung**: "___"
**Bei Handel**: "___"
**Bei Ablehnung**: "___"
**Bei Freundschaft**: "___"

```

---

## 👨‍💼 Beispiel-NPC: Händler Boran

```markdown
# Boran der Reisende

**Rasse**: Terraner
**Beruf/Rolle**: Reisender Händler
**Alter**: 45
**Geschlecht**: Männlich

---

## Persönlichkeit

**Charakterzüge**: Freundlich, geschäftstüchtig, etwas ängstlich
**Motivation**: Reichtum anhäufen, seine Familie ernähren
**Ängste/Schwächen**: Angst vor Räubern und Monstern, spielt nicht gerne den Helden
**Besonderheiten**: Kennt viele Gerüchte und Geschichten aus verschiedenen Städten

---

## Aussehen

**Größe**: 1,75m
**Statur**: Etwas rundlich, gut genährt
**Haare**: Braun, schon leicht ergraut
**Augen**: Braun, freundlich
**Kleidung**: Praktische Reisekleidung, breiter Hut, immer eine Geldkatze am Gürtel
**Besondere Merkmale**: Buschiger Schnurrbart

---

## Attribute

- **Stärke**: 6 (Bonus: 3)
- **Geschicklichkeit**: 8 (Bonus: 4)
- **Konstitution**: 7 (Bonus: 4)
- **Intelligenz**: 9 (Bonus: 5)
- **Weisheit**: 8 (Bonus: 4)
- **Charisma**: 10 (Bonus: 5)

---

## Fähigkeiten

- **Überzeugung**: Stufe 5
  - **Spezialisierung: Handel**: Stufe 4
- **Gelehrsamkeit**: Stufe 3
  - **Spezialisierung: Geografie**: Stufe 2

---

## Beziehungen

- **Familie**: Frau Mira, zwei Kinder in Adventuria
- **Freunde**: Verschiedene Händler und Gastwirte entlang seiner Route
- **Feinde**: Konkurrierender Händler Gregor (hasst ihn)
- **Organisation**: Händler-Gilde von Adventuria (Mitglied)

---

## Hintergrund

Boran ist seit 20 Jahren als reisender Händler unterwegs. Er bereist die Straßen zwischen Adventuria, Valoria und den Ländern der Mitte. Seine Karawane ist klein, aber gut sortiert. Er verkauft alles von Alltagswaren bis zu seltenen Fundstücken, die er auf seinen Reisen findet.

Vor 5 Jahren wurde er von Räubern überfallen und fast getötet. Seitdem ist er vorsichtig und zahlt gerne für Geleitschutz. Er hat viele Geschichten zu erzählen und ist eine gute Informationsquelle über die Geschehnisse in verschiedenen Städten.

---

## Quest-Potential

**Mögliche Quests**:
- **Geleitschutz**: Boran braucht Schutz auf seiner nächsten Reise (Bezahlung: 20 G + Rabatt auf Waren)
- **Verlorene Ware**: Räuber haben seine Karawane überfallen, er bittet die Spieler, seine Waren zurückzuholen (Belohnung: 50 G + seltener Gegenstand)
- **Familiendrama**: Borans Sohn ist verschwunden, er braucht Hilfe beim Suchen (Belohnung: Große Summe + lebenslange Dankbarkeit)

**Belohnungen**:
- Geld
- Seltene Handelswaren mit Rabatt
- Informationen über Gerüchte und Ereignisse

---

## Handelswaren

| **Item** | **Preis** | **Verfügbarkeit** |
|----------|-----------|-------------------|
| Heiltrank | 25 G | 3 auf Lager |
| Reiseproviant (5 Tage) | 5 S | Unbegrenzt |
| Seil (15m) | 1 S | 10 auf Lager |
| Karte (Region) | 8 S | 2 auf Lager |
| Glücksbringer-Amulett | 15 G | 1 auf Lager (gibt +1 auf nächsten Wurf) |

---

## Dialog-Beispiele

**Begrüßung**: "Ah, Reisende! Willkommen, willkommen! Boran ist mein Name, und ich habe die besten Waren weit und breit!"

**Bei Handel**: "Für euch, meine Freunde, ein Sonderpreis! Nun ja... vielleicht ein kleiner Rabatt, wenn ihr mehr kauft!"

**Bei Ablehnung**: "Kein Problem, kein Problem! Schaut euch um, vielleicht findet ihr doch noch etwas."

**Bei Freundschaft**: "Ihr seid gute Leute. Wenn ihr je in Schwierigkeiten seid, kommt zu Boran. Ich schulde euch was!"

```

---

## 🗡️ Elite-Gegner-Template: Ork-Häuptling

```markdown
# Ork-Häuptling Grak der Zerstörer

**Typ**: Humanoid (Elite)
**Schwierigkeitsgrad**: Elite
**Größe**: Riesig

---

## Attribute

- **Stärke**: 14 (Bonus: 7)
- **Geschicklichkeit**: 8 (Bonus: 4)
- **Konstitution**: 12 (Bonus: 6)
- **Intelligenz**: 6 (Bonus: 3)
- **Weisheit**: 6 (Bonus: 3)
- **Charisma**: 8 (Bonus: 4)

---

## Kampfwerte

- **Lebenspunkte (LP)**: 55
- **Rüstungswert**: 6 (Schuppenpanzer)
- **Initiative**: 4
- **Bewegungsreichweite**: 10 Meter

---

## Angriffe

### Zweihand-Kriegsaxt "Schädelbrecher"
- **Typ**: Nahkampf
- **Trefferprobe**: 2W6 + 7 (Stärke) + 5 (Nahkampf) = 2W6 + 12
- **Schaden**: 2W6 + 6
- **Reichweite**: Nahkampf
- **Besonderheiten**: 
  - **Mächtiger Schlag**: Kann 1x pro Kampf einen verheerenden Schlag ausführen (3W6 + 8 Schaden, aber -4 auf Verteidigung in dieser Runde)
  - **Spalten**: Bei kritischem Treffer (12) ignoriert der Angriff Rüstung

### Kriegsschrei
- **Typ**: Spezialfähigkeit
- **Reichweite**: 15 Meter Radius
- **Effekt**: Alle Verbündeten erhalten +2 auf Angriffe für 3 Runden, Gegner müssen Weisheits-Probe (Schwierigkeit 16) bestehen oder sind eingeschüchtert (-2 auf alle Proben für 2 Runden)
- **Nutzung**: 1x pro Kampf

---

## Verteidigung

- **Ausweichen**: 2W6 + 4
- **Kampf-Instinkt**: Kann 1x pro Runde einen Angriff parieren (2W6 + 7)
- **Legendäre Zähigkeit**: Bei 0 LP kann er 1x pro Tag einen Rettungswurf machen (Schwierigkeit 14). Bei Erfolg bleibt er bei 1 LP stehen.

---

## Fähigkeiten & Eigenschaften

- **Nahkampf**: 5
  - **Spezialisierung: Zweihandwaffen**: 4
- **Einschüchterung**: 4
- **Taktik**: 2
- **Berserker-Wut**: Bei unter 20 LP: +4 auf Angriffe, +1W6 Schaden, aber -3 auf Verteidigung
- **Alphastellung**: Alle Orks in 20m Reichweite erhalten +1 auf Moral-Proben
- **Kampferfahren**: +2 auf Initiative

---

## Resistenzen & Schwächen

- **Resistent gegen**: Gift, Angst
- **Schwach gegen**: Heilige Magie (doppelter Schaden)
- **Immun gegen**: Einschüchterung

---

## Verhalten & Taktik

**Kampfstil**: Führt von vorne, stürmt auf stärksten Gegner zu, nutzt Kriegsschrei zu Beginn des Kampfes
**Intelligenz**: Überdurchschnittlich für einen Ork, versteht Grundlagen der Taktik
**Sozialverhalten**: Wird nur durch Stärke respektiert, tötet schwache Untergebene

---

## Beute & Belohnungen

- **Loot**:
  - Zweihand-Kriegsaxt "Schädelbrecher" (+2 Schaden, 150 G Wert)
  - Schuppenpanzer (6 Rüstung, 50 G)
  - Ork-Häuptlings-Helm (Trophäe, 20 G)
  - Häuptlings-Banner (kann Ork-Truppen beeindrucken)
  - 2W6 Goldmünzen
- **Erfahrung**: 50 XP
- **Besondere Drops**: Runen-Talisman (gibt +1 auf Stärke-Proben, 100 G)

---

## Beschreibung

Grak ist ein riesiger Ork mit vernarbter, dunkelgrüner Haut und brennend roten Augen. Er trägt einen massiven Schuppenpanzer und einen Helm aus dem Schädel eines Drachen (so behauptet er zumindest). Seine Zweihand-Kriegsaxt "Schädelbrecher" ist mit den Runen vergangener Schlachten beschriftet.

Als Häuptling führt er einen Stamm von 40-50 Orks und ist für seine Brutalität bekannt. Er hat bereits drei Dörfer in Sunar niedergebrannt und gilt als einer der gefährlichsten Ork-Anführer an der Front.

**Taktik im Kampf**: Grak beginnt mit seinem Kriegsschrei, um seine Truppen zu stärken und Gegner einzuschüchtern. Dann stürmt er auf den stärksten oder am besten gerüsteten Gegner zu. Wenn er unter 20 LP fällt, verfällt er in Berserker-Wut und kämpft bis zum Tod.

```

---

## 📊 Schnell-Skalierungs-Tabelle

Nutze diese Tabelle, um Monster schnell für verschiedene Level anzupassen:

|**Level-Bereich**|**LP-Multiplikator**|**Angriffs-Bonus**|**Schadens-Bonus**|**Rüstungs-Bonus**|
|---|---|---|---|---|
|1-2 (Anfänger)|x1|+0|+0|+0|
|3-4 (Fortgeschritten)|x1.5|+1|+1|+1|
|5-6 (Erfahren)|x2|+2|+2|+2|
|7-8 (Veteran)|x2.5|+3|+1W6|+3|
|9-10 (Meister)|x3|+4|+1W6|+4|
|11-12 (Legendär)|x4|+5|+2W6|+5|

**Beispiel**: Ein Waldwolf (12 LP, 2W6+4 Angriff, 1W6+2 Schaden, 2 Rüstung) für Level 5-6 Spieler:

- LP: 12 x 2 = **24 LP**
- Angriff: 2W6 + 4 + 2 = **2W6 + 6**
- Schaden: 1W6 + 2 + 2 = **1W6 + 4**
- Rüstung: 2 + 2 = **4 Rüstung**

---

**Zusammenfassung:** Ich habe ein vollständiges Template-System für Bestarium und NPCs erstellt mit:

- Blank-Templates zum Ausfüllen
- Beispiel-Monster (Waldwolf, Ork-Krieger, Ork-Häuptling)
- Beispiel-NPC (Händler Boran)
- Schwierigkeitsgrade-System
- Schnell-Skalierungs-Tabelle für verschiedene Level

Möchtest du weitere Beispiel-Monster/NPCs oder soll ich spezifische Kreaturen-Typen ausarbeiten (z.B. Untote, Dämonen, Drachen)?