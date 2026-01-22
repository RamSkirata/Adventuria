
```

## characterName: "" rasse: "" klasse: "" level: 1 staerke: 0 geschicklichkeit: 0 konstitution: 0 intelligenz: 0 weisheit: 0 charisma: 0 magie: 0 technik: 0 lebenspunkte: 0 maxLebenspunkte: 0 manapunkte: 0 maxManapunkte: 0 ruestungswert: 0 kupfer: 0 silber: 0 gold: 0 platin: 0 stern: 0

# `=this.characterName`

> [!info] Charakterinformationen **Rasse**: `=this.rasse` **Klasse**: `=this.klasse` **Level**: `=this.level`

```



## 📊 Attribute

| Attribut             | Wert                      | Bonus (Wert/2)                      |
| -------------------- | ------------------------- | ----------------------------------- |
| **Stärke**           | `12=this.staerke`         | `=round(this.staerke / 2)`          |
| **Geschicklichkeit** | `8=this.geschicklichkeit` | `=round(this.geschicklichkeit / 2)` |
| **Konstitution**     | `10=this.konstitution`    | `=round(this.konstitution / 2)`     |
| **Intelligenz**      | `5=this.intelligenz`      | `=round(this.intelligenz / 2)`      |
| **Weisheit**         | `3=this.weisheit`         | `=round(this.weisheit / 2)`         |
| **Charisma**         | `7=this.charisma`         | `=round(this.charisma / 2)`         |
| **Magie**            | `=this.magie`             | -                                   |
| **Technik**          | `=this.technik`           | -                                   |

> [!tip] Attribut-Summe **Gesamt**: `=this.staerke + this.geschicklichkeit + this.konstitution + this.intelligenz + this.weisheit + this.charisma + this.magie + this.technik` _(Sollte zwischen 35 und 70 liegen)_

---

## ⚔️ Kampfwerte

> [!danger] Lebenspunkte **Aktuell**: `=this.lebenspunkte` / **Maximum**: `=this.maxLebenspunkte`
> 
> **Berechnung LP**: 2W6 + (Stärke/2) + (Konstitution/2)

> [!info] Manapunkte **Aktuell**: `=this.manapunkte` / **Maximum**: `=this.maxManapunkte`
> 
> **Berechnung MP**: 2W6 + (Intelligenz/2) + (Weisheit/2) + Magie

> [!note] Rüstung **Rüstungswert**: `=this.ruestungswert`

---

## 🎯 Fähigkeiten

### Kampf-Fähigkeiten

#### Nahkampf (Stärke)

- [ ] **Nahkampf** - Stufe: ___/12 | Bonus: ___
    - [ ] **Spezialisierung: Einhandschwert** - Stufe: ___/6
    - [ ] **Spezialisierung: Zweihandschwert** - Stufe: ___/6
    - [ ] **Spezialisierung: Einhandaxt** - Stufe: ___/6
    - [ ] **Spezialisierung: Zweihandaxt** - Stufe: ___/6
    - [ ] **Spezialisierung: Hammer & Kolben** - Stufe: ___/6
    - [ ] **Spezialisierung: Stangenwaffen** - Stufe: ___/6
    - [ ] **Spezialisierung: Dolche** - Stufe: ___/6
    - [ ] **Spezialisierung: Rapier & Degen** - Stufe: ___/6

#### Fernkampf (Geschicklichkeit)

- [ ] **Fernkampf** - Stufe: ___/12 | Bonus: ___
    - [ ] **Spezialisierung: Langbogen** - Stufe: ___/6
    - [ ] **Spezialisierung: Kurzbogen** - Stufe: ___/6
    - [ ] **Spezialisierung: Armbrust** - Stufe: ___/6
    - [ ] **Spezialisierung: Wurfwaffen** - Stufe: ___/6
    - [ ] **Spezialisierung: Schleuder** - Stufe: ___/6

#### Waffenloser Kampf (Stärke/Geschicklichkeit)

- [ ] **Waffenloser Kampf** - Stufe: ___/12 | Bonus: ___
    - [ ] **Spezialisierung: Faustkampf** - Stufe: ___/6
    - [ ] **Spezialisierung: Ringen** - Stufe: ___/6
    - [ ] **Spezialisierung: Mönchskampf** - Stufe: ___/6

#### Verteidigung (Geschicklichkeit/Konstitution)

- [ ] **Verteidigung** - Stufe: ___/12 | Bonus: ___
    - [ ] **Spezialisierung: Ausweichen** - Stufe: ___/6
    - [ ] **Spezialisierung: Parieren** - Stufe: ___/6
    - [ ] **Spezialisierung: Blocken (Schild)** - Stufe: ___/6

#### Taktik (Intelligenz)

- [ ] **Taktik** - Stufe: ___/12 | Bonus: ___

---

### Soziale Fähigkeiten

#### Überzeugung (Charisma)

- [ ] **Überzeugung** - Stufe: ___/12 | Bonus: ___
    - [ ] **Spezialisierung: Überreden** - Stufe: ___/6
    - [ ] **Spezialisierung: Verhandeln** - Stufe: ___/6
    - [ ] **Spezialisierung: Diplomatie** - Stufe: ___/6

#### Täuschung (Charisma)

- [ ] **Täuschung** - Stufe: ___/12 | Bonus: ___
    - [ ] **Spezialisierung: Lügen** - Stufe: ___/6
    - [ ] **Spezialisierung: Bluffen** - Stufe: ___/6
    - [ ] **Spezialisierung: Verkleiden** - Stufe: ___/6

#### Einschüchterung (Stärke/Charisma)

- [ ] **Einschüchterung** - Stufe: ___/12 | Bonus: ___

#### Auftreten (Charisma)

- [ ] **Auftreten** - Stufe: ___/12 | Bonus: ___
    - [ ] **Spezialisierung: Führung** - Stufe: ___/6
    - [ ] **Spezialisierung: Performance** - Stufe: ___/6
    - [ ] **Spezialisierung: Etikette** - Stufe: ___/6

---

### Wissens-Fähigkeiten

#### Gelehrsamkeit (Intelligenz)

- [ ] **Gelehrsamkeit** - Stufe: ___/12 | Bonus: ___
    - [ ] **Spezialisierung: Geschichte** - Stufe: ___/6
    - [ ] **Spezialisierung: Arkanes Wissen** - Stufe: ___/6
    - [ ] **Spezialisierung: Religionen** - Stufe: ___/6

#### Naturkunde (Weisheit)

- [ ] **Naturkunde** - Stufe: ___/12 | Bonus: ___
    - [ ] **Spezialisierung: Tierkunde** - Stufe: ___/6
    - [ ] **Spezialisierung: Pflanzenkunde** - Stufe: ___/6
    - [ ] **Spezialisierung: Wetterkunde** - Stufe: ___/6

#### Medizin (Intelligenz/Weisheit)

- [ ] **Medizin** - Stufe: ___/12 | Bonus: ___
    - [ ] **Spezialisierung: Erste Hilfe** - Stufe: ___/6
    - [ ] **Spezialisierung: Chirurgie** - Stufe: ___/6
    - [ ] **Spezialisierung: Kräuterheilkunde** - Stufe: ___/6

---

### Handwerks-Fähigkeiten

#### Handwerk (Geschicklichkeit)

- [ ] **Handwerk** - Stufe: ___/12 | Bonus: ___

#### Technik (Intelligenz)

- [ ] **Technik** - Stufe: ___/12 | Bonus: ___
    - [ ] **Spezialisierung: Waffenbau** - Stufe: ___/6
    - [ ] **Spezialisierung: Rüstungsschmied** - Stufe: ___/6
    - [ ] **Spezialisierung: Fallenbau** - Stufe: ___/6
    - [ ] **Spezialisierung: Belagerungstechnik** - Stufe: ___/6
    - [ ] **Spezialisierung: Feinmechanik** - Stufe: ___/6
    - [ ] **Spezialisierung: Sprengstoff** - Stufe: ___/6
    - [ ] **Spezialisierung: Schiffbau** - Stufe: ___/6
    - [ ] **Spezialisierung: Konstruktion** - Stufe: ___/6

#### Magie (Intelligenz/Weisheit)

- [ ] **Magie** - Stufe: ___/12 | Bonus: ___
    - [ ] **Spezialisierung: Heilige Magie** - Stufe: ___/6
    - [ ] **Spezialisierung: Naturmagie** - Stufe: ___/6
    - [ ] **Spezialisierung: Shaper-Magie** - Stufe: ___/6
    - [ ] **Spezialisierung: Feuermagie** - Stufe: ___/6
    - [ ] **Spezialisierung: Wassermagie** - Stufe: ___/6
    - [ ] **Spezialisierung: Erdmagie** - Stufe: ___/6
    - [ ] **Spezialisierung: Luftmagie** - Stufe: ___/6
    - [ ] **Spezialisierung: Evokation** - Stufe: ___/6
    - [ ] **Spezialisierung: Illusion** - Stufe: ___/6
    - [ ] **Spezialisierung: Veränderung** - Stufe: ___/6
    - [ ] **Spezialisierung: Beschwörung** - Stufe: ___/6
    - [ ] **Spezialisierung: Erkenntnis** - Stufe: ___/6
    - [ ] **Spezialisierung: Schutz** - Stufe: ___/6
    - [ ] **Spezialisierung: Runenmagie** - Stufe: ___/6

---

### Überleben-Fähigkeiten

#### Überleben (Weisheit)

- [ ] **Überleben** - Stufe: ___/12 | Bonus: ___
    - [ ] **Spezialisierung: Fährtenlesen** - Stufe: ___/6
    - [ ] **Spezialisierung: Kräuterkunde** - Stufe: ___/6
    - [ ] **Spezialisierung: Nahrungssuche** - Stufe: ___/6
    - [ ] **Spezialisierung: Orientierung** - Stufe: ___/6

#### Schleichen (Geschicklichkeit)

- [ ] **Schleichen** - Stufe: ___/12 | Bonus: ___
    - [ ] **Spezialisierung: Verstecken** - Stufe: ___/6
    - [ ] **Spezialisierung: Leise Bewegung** - Stufe: ___/6
    - [ ] **Spezialisierung: Schattentanz** - Stufe: ___/6

#### Diebeskunst (Geschicklichkeit)

- [ ] **Diebeskunst** - Stufe: ___/12 | Bonus: ___
    - [ ] **Spezialisierung: Schlösser knacken** - Stufe: ___/6
    - [ ] **Spezialisierung: Taschendiebstahl** - Stufe: ___/6
    - [ ] **Spezialisierung: Fallen entschärfen** - Stufe: ___/6

---

## 🎒 Inventar

### Waffen

|Waffe|Schaden|Attribut|Besonderheiten|
|---|---|---|---|
|||||
|||||
|||||

### Rüstung

|Rüstungsteil|Rüstwert|Besonderheiten|
|---|---|---|
||||
||||

### Ausrüstung

- [ ]
- [ ]
- [ ]
- [ ]
- [ ]

### Magische Gegenstände

- [ ]
- [ ]
- [ ]

---

## 💰 Währung

|Münze|Anzahl|
|---|---|
|**Kupfer**|`=this.kupfer`|
|**Silber**|`=this.silber`|
|**Gold**|`=this.gold`|
|**Platin**|`=this.platin`|
|**Stern**|`=this.stern`|

**Gesamtwert in Kupfer**: `=this.kupfer + (this.silber * 10) + (this.gold * 100) + (this.platin * 1000) + (this.stern * 10000)`

---

## 📜 Gelernte Zauber

### Heilige Magie

- [ ]
- [ ]

### Naturmagie

- [ ]
- [ ]

### Shaper-Magie

- [ ]
- [ ]

### Element-Magie

- [ ]
- [ ]

### Akademie-Zauber

- [ ]
- [ ]

---

## 🔧 Technische Erfindungen

- [ ]
- [ ]
- [ ]

---

## 📝 Notizen

### Hintergrundgeschichte

### Ziele

### Verbündete & Kontakte

### Feinde

---

## 📊 Dataview-Übersicht

```dataview
TABLE
  level as "Level",
  rasse as "Rasse",
  klasse as "Klasse",
  lebenspunkte as "LP",
  manapunkte as "MP"
WHERE file.name = this.file.name
```