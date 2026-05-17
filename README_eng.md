<div align="center">
  
  # 🌱 Smart Garden Irrigation
  
</div>

<div align="center">

[![README Deutsch](https://img.shields.io/badge/README-DE-orange)](https://github.com/jayjojayson/HA-smart-garden-irrigation/blob/main/README.md)
[![Support](https://img.shields.io/badge/%20-Support%20Me-steelblue?style=flat&logo=paypal&logoColor=white)](https://www.paypal.me/quadFlyerFW)

</div>

<p align="center">
  <a href="https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https%3A%2F%2Fraw.githubusercontent.com%2Fjayjojayson%2FHA-smart-garden-irrigation%2Fmain%2Fsmart_garden_irrigation.yaml">
    <img width="250" alt="Import Blueprint" src="https://github.com/user-attachments/assets/fa01530a-1d52-4b2b-b637-1269bd0cd747">
  </a>
</p>

---

### Description

Intelligent control of your garden irrigation — flexible, solar-optimized and fully automatic.  
The blueprint supports up to **4 irrigation modes**, which can be used individually or in combination.

---

### 🎯 Irrigation Modes

| Mode | Description |
|------|-------------|
| ⏰ **Schedule Helper** | Trigger irrigation via a HA Schedule helper |
| 🕐 **Fixed Times** | Up to 3 individual times per day |
| 🔄 **Rhythm Control** | Every X hours within a configurable time window |
| ☀️ **Solar Surplus** | Automatic start when sufficient solar power is available |

---

### 🛡️ Protection Mechanisms

| Protection | Description |
|------------|-------------|
| 🌧️ **Rain Sensor Lock** | Stops irrigation during rainfall — configurable threshold in L/m² |
| 🔋 **Battery Storage Lock** | Only irrigate when the home battery has reached a minimum SoC |
| 🔢 **Daily Limit** | Maximum number of starts per day |
| 💧 **Water Limit** | Stops after a configurable number of liters per cycle |
| 🔌 **Master Switch** | Global on/off lock for the entire irrigation system |

---

### 📋 Requirements

**Required:**
- ✅ At least one `switch` entity for your irrigation
- ✅ An `input_number` helper as a daily start counter (e.g. `input_number.irrigation_starts_today`, min=0, max=10, step=1)

**Optional (depending on which modes you use):**
- ➕ Solar surplus sensor (Watts, `device_class: power`)
- ➕ Precipitation sensor (Liters/m²)
- ➕ Battery SoC sensor (%, `device_class: battery`)
- ➕ Water consumption sensor (Liters)
- ➕ Solar forecast sensor (kWh, e.g. Solcast or Forecast.Solar)
- ➕ `input_datetime` helper for the minimum interval between solar starts (e.g. `input_datetime.irrigation_solar_last_run`)

---

### ⚙️ Configuration

The blueprint is organized into clear, collapsible sections:

1. **Devices & Basic Settings** — Switches, irrigation duration, daily limit
2. **Schedule Helper** — Enable and select the Schedule helper
3. **Fixed Times** — Enable and configure up to 3 daily times
4. **Rhythm Control** — Set the interval (hours) and time window
5. **Solar Surplus Control** — Threshold, hysteresis, time window, forecast and minimum interval
6. **Global Locks** — Rain sensor, master switch, battery SoC and water limit

> 💡 **Tip:** Only open the sections you actually need — the rest stays collapsed and out of the way.

---

### 🚀 Installation

1. Click the **"Import Blueprint"** button at the top of this page.
2. Confirm the import in your Home Assistant instance.
3. Go to **Settings → Automations → Blueprints** and create a new automation.
4. Select the **"Smarte Gartenbewässerung"** blueprint.
5. Configure the desired sections and save.

---

### 🔧 Creating Helpers (Example)

In Home Assistant under **Settings → Devices & Services → Helpers**:

- **Daily counter:** `input_number.irrigation_starts_today`  
  Type: Number, Min: 0, Max: 10, Step: 1, Display mode: Slider

- **Solar timestamp:** `input_datetime.irrigation_solar_last_run`  
  Type: Date and time

---

### 📄 License

This project is licensed under the [MIT License](LICENSE).
