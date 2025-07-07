# RdG MultiCircle Card

A configurable, responsive **3×2 grid card** showing up to **six animated circle graphs**.  
Perfect for comparing energy consumption, production, temperatures or any numeric sensors — all in a clean dashboard layout.

![Preview](preview.gif)

---

## 🔧 Features

- ➕ Supports 3 to 6 sensors in a 3-column by 2-row layout
- 🌀 Each circle uses the [RdG Circle Card](https://github.com/rjdgroot/rdg-circle-card)
- 🎨 Individual per-sensor styling (colors, stroke, alert values)
- 🧾 Optional labels below each circle
- 🧩 Fully embeddable, no outer `ha-card` frame
- 📱 Fully responsive layout using `clamp(...)` sizing
- ⚡ Tap actions per sensor: `more-info`, `navigate`, `call-service`, `toggle`, or `none`

---

## 📦 Installation

### Option 1: HACS (recommended)

1. Add this repository as a **custom repository** in HACS:
2. Go to HACS → Frontend → Explore & Download Repositories
3. Search for **"RdG MultiCircle Card"**, install and reload

### Option 2: Manual

1. Copy `rdg-multicircle-card.js` (and `rdg-circle-card.js`) to `/config/www/rdg-multicircle-card/`
2. Add this to your `configuration.yaml` or UI resources:

```yaml
resources:
- url: /local/rdg-multicircle-card/rdg-multicircle-card.js
 type: module
```
## 🧪 Example Usage
```
type: custom:rdg-multicircle-card
show_labels: true
stroke_width: 10
stroke_bg_width: 6
stroke_bg_color: "#cccccc"
circle_1:
  entity: sensor.energy_import
  name: Import
  icon: mdi:transmission-tower
  stroke_color_positive: "#03a9f4"
  stroke_color_negative: "#4caf50"
  min: -10
  max: 10
  units: "kWh"
  decimals: 1
circle_2:
  ...
circle_3:
 ...

# Optional additional circles (4-6)
circle_4:
  entity: sensor.temperature_1
  name: Living Room
  stroke_color: "#ff5722"
  min: 0
  max: 30
circle_5:
  ...
circle_6:
  ...
```
## ⚙️ Configuration Options
<table> <thead> <tr> <th>Option</th> <th>Type</th> <th>Description</th> </tr> </thead> <tbody> <tr><td><code>show_labels</code></td><td>boolean</td><td>Show text label under each circle (default: true)</td></tr> <tr><td><code>stroke_width</code></td><td>number</td><td>Default stroke width for all circles (can be overridden per circle)</td></tr> <tr><td><code>stroke_bg_width</code></td><td>number</td><td>Default background stroke width</td></tr> <tr><td><code>stroke_bg_color</code></td><td>string</td><td>Default background stroke color</td></tr> </tbody> </table>
Each circle_X (from 1 to 6) supports the full configuration from the rdg-circle-card, such as:

entity
icon, name
min, max, units, decimals
stroke_color, stroke_color_positive, stroke_color_negative
alert_value
tap_action
attribute, attribute_max, show_max
etc.

## 📘 License
Created by Rinse de Groot
