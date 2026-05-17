<div align="center">
  
  # 🌱 Smarte Gartenbewässerung
  
</div>

<div align="center">
  
[![README English](https://img.shields.io/badge/README-EN-blue)](https://github.com/jayjojayson/HA-smart-garden-irrigation/blob/main/README_eng.md)
[![Support](https://img.shields.io/badge/%20-Support%20Me-steelblue?style=flat&logo=paypal&logoColor=white)](https://www.paypal.me/quadFlyerFW)

</div>

<p align="center">
  <a href="https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https%3A%2F%2Fraw.githubusercontent.com%2Fjayjojayson%2FHA-smart-garden-irrigation%2Fmain%2Fsmart_garden_irrigation.yaml">
    <img width="250" alt="Blueprint importieren" src="https://github.com/user-attachments/assets/fa01530a-1d52-4b2b-b637-1269bd0cd747">
  </a>
</p>

---

### Beschreibung

Intelligente Steuerung deiner Gartenbewässerung — flexibel, solar-optimiert und vollautomatisch.  
Der Blueprint unterstützt bis zu **4 Bewässerungsmodi**, die sich einzeln oder in Kombination nutzen lassen.

---

### 🎯 Bewässerungsmodi

| Modus | Beschreibung |
|-------|-------------|
| ⏰ **Zeitplan-Helfer** | Starte die Bewässerung über einen HA-Schedule-Helfer |
| 🕐 **Feste Uhrzeiten** | Bis zu 3 individuelle Uhrzeiten pro Tag |
| 🔄 **Rhythmussteuerung** | Alle X Stunden innerhalb eines einstellbaren Zeitfensters |
| ☀️ **Solarüberschuss** | Automatischer Start bei ausreichend Solarüberschuss |

---

### 🛡️ Schutzmechanismen

| Schutz | Beschreibung |
|--------|-------------|
| 🌧️ **Regensensor-Sperre** | Stoppt die Bewässerung bei Niederschlag — einstellbarer Schwellenwert in L/m² |
| 🔋 **Batteriespeicher-Sperre** | Erst bewässern, wenn der Hausspeicher einen Mindest-SoC erreicht hat |
| 🔢 **Tageslimit** | Maximale Anzahl an Starts pro Tag |
| 💧 **Wasserlimit** | Stoppt nach einer einstellbaren Literzahl pro Durchgang |
| 🔌 **Haupt-Schalter** | Globale Ein/Aus-Sperre für die gesamte Bewässerung |

---

### 📋 Voraussetzungen

**Pflicht:**
- ✅ Mindestens einen `switch`-Schalter für die Bewässerung
- ✅ Einen `input_number`-Helfer als Tageszähler (z. B. `input_number.bewaesserung_starts_heute`, min=0, max=10, step=1)

**Optional (je nach verwendetem Modus):**
- ➕ Sensor für Solarüberschuss (Watt, `device_class: power`)
- ➕ Sensor für Niederschlag (Liter/m²)
- ➕ Sensor für Batteriespeicher-SoC (%, `device_class: battery`)
- ➕ Sensor für Wasserverbrauch (Liter)
- ➕ Sensor für Solarvorhersage (kWh, z. B. Solcast oder Forecast.Solar)
- ➕ `input_datetime`-Helfer für den Mindestabstand zwischen Solar-Starts (z. B. `input_datetime.bewaesserung_solar_letzter_start`)

---

### ⚙️ Konfiguration

Der Blueprint ist in übersichtliche, einklappbare Sektionen unterteilt:

1. **Geräte & Grundeinstellungen** — Schalter, Bewässerungsdauer, Tageslimit
2. **Zeitplan-Helfer** — Aktivierung und Auswahl des Schedule-Helfers
3. **Feste Uhrzeiten** — Bis zu 3 Uhrzeiten aktivieren und konfigurieren
4. **Rhythmussteuerung** — Intervall (Stunden) und Zeitfenster festlegen
5. **Solarüberschuss-Steuerung** — Schwellenwert, Hysterese, Zeitfenster, Vorhersage und Mindestabstand
6. **Globale Sperren** — Regensensor, Haupt-Schalter, Batterie-SoC und Wasserlimit

> 💡 **Tipp:** Öffne nur die Sektionen, die du wirklich brauchst — der Rest bleibt zugeklappt und stört nicht.

---

### 🚀 Installation

1. Klicke auf den **„Blueprint importieren"**-Button oben auf dieser Seite.
2. Bestätige den Import in deiner Home Assistant-Instanz.
3. Gehe zu **Einstellungen → Automationen → Blueprints** und erstelle eine neue Automation.
4. Wähle den Blueprint **„Smarte Gartenbewässerung"** aus.
5. Konfiguriere die gewünschten Sektionen und speichere.

---

### 🔧 Helfer erstellen (Beispiel)

In Home Assistant unter **Einstellungen → Geräte & Dienste → Helfer**:

- **Tageszähler:** `input_number.bewaesserung_starts_heute`  
  Typ: Zahl, Min: 0, Max: 10, Schrittweite: 1, Anzeigemodus: Regler

- **Solar-Zeitstempel:** `input_datetime.bewaesserung_solar_letzter_start`  
  Typ: Datum und Uhrzeit

---

### 📄 Lizenz

Dieses Projekt steht unter der [MIT-Lizenz](LICENSE).
