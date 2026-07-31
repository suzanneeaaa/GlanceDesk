# Hardware Specifications & Assembly: GlanceDesk

## 🛠️ Bill of Materials (BOM)

| Component | Part / Specification | Function & Integration Notes | Qty |
| :--- | :--- | :--- | :--- |
| **Main All-In-One Board** | LilyGO T5 4.7" E-Paper V2.3 (Touch) | ESP32-S3-WROOM-1-N16R8, 4.7" E-Paper, capacitive touch, TP4056 onboard | 1 |
| **Power Source** | 	3.7V 2000mAh Li-Po Battery (JST-PH 2.0, verify polarity before connecting) | Plugs into onboard connector | 1 |
| **Fuel Gauge IC** | MAX17048 (I2C) | Accurate state-of-charge; shares existing I2C bus (IO17/18) | 1 |
| **Audio Amplifier** | MAX98357A I2S DAC Module | Needs 3 free GPIOs (BCLK/LRCLK/DIN) — confirm against real schematic | 1 |
| **Decoupling Capacitors** | 220–470µF electrolytic + 0.1µF ceramic, near MAX98357A VDD|Prevents rail sag from speaker peaks| 1 set|
| **Speaker** | 8Ω 1W / 2W Micro-Speaker | Compact internal audio driver wired to MAX98357A output terminals. | 1 |
| **Ambient Light** | 	SK6812 NeoPixel Ring (8–12 LEDs) | 3.3V-logic-tolerant, no level shifter needed. Runs dimmer/color-shifted on raw 3.7V battery, full brightness on USB 5V | 1 |
| **Physical Input** | 6mm Tactile Push Button | External wake-up switch | 1 |
| **GPIO Expander (contingency)** | PCF8574 or MCP23017 (I2C)| Add only if final pin count for I2S + LED + button comes up short once GPIO33–37 (Octal PSRAM) and GPIO26-32 (flash/PSRAM) are excluded | 1 |
| **Enclosure** | Custom 3D Printed |~135 mm x 80 mm x 65 mm box housing with translucent top rim diffuser for LED ring. | 1 |

## 📐Dimensions
| Component | Part / Specification | Dimensions (L × W × H) | Notes |
| :--- | :--- | :--- | :--- |
| **Main Board** | LilyGO T5 4.7" E-Paper V2.4 (Touch) | ~121 × 67 mm (board), panel is 4.7" diagonal, 540×960px | Board thickness with connectors/battery clip is roughly 8–10mm |
| **Power Source** | 3.7V 2000mAh Li-Po | ~55 × 48 × 8 mm (typical for flat 2000mAh cell) | Confirm against exact SKU; capacity-to-size ratio varies with cell shape |
| **Fuel Gauge IC** | MAX17048 breakout (e.g. Adafruit #5580) | 25.7 × 20.3 × 7.2 mm | JST-PH battery ports on board — check mechanical clearance relative to main board's battery connector |
| **Audio Amplifier** | MAX98357A breakout (e.g. Adafruit #3006) | 19.4 × 17.8 × 3.0 mm | Very compact, easy to position |
| **Decoupling Capacitors** | 220–470µF electrolytic + 0.1µF ceramic | ~6.3 × 11 mm (electrolytic, radial); ceramic negligible (~3×2mm) | Electrolytic footprint can dominate at small scale — plan clearance near amp |
| **Speaker** | 8Ω 1W/2W micro-speaker | ~28–40mm diameter × 5–8mm thick (round) or ~20×30×4mm (oval/rectangular) | Highly dependent on selected model — primary driver of enclosure depth |
| **Ambient Light** | SK6812 ring, 8 or 12 LEDs | 8-LED: ~28–35mm outer dia; 12-LED: ~44–45mm outer dia (~4mm thick) | Diameter scales with LED count — set early to fix diffuser cutout dimensions |
| **Physical Input** | 6mm tactile push button | 6 × 6 mm footprint, ~3.5–5mm tall | Standard through-hole size |
| **GPIO Expander (contingency)** | PCF8574 breakout | ~25 × 20 × 3 mm | Optional — add only if GPIO count is insufficient |
| **Enclosure** | Custom 3D printed | 135 × 80 × 65 mm | Verify internal clearance against speaker + battery + main board stack-up |
