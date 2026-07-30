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


