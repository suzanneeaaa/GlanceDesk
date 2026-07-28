# Hardware Specifications & Assembly: GlanceDesk

## 🛠️ Bill of Materials (BOM)

| Component | Part / Specification | Function & Integration Notes | Qty |
| :--- | :--- | :--- | :--- |
| **Main All-In-One Board** | LilyGO T5 4.7" E-Paper V2.3 (Touch) | Integrates ESP32-S3, 4.7" E-Paper display, capacitive touch controller, and TP4056 charging IC. | 1 |
| **Power Source** | 3.7V 1000mAh–2000mAh Li-Po Battery | Plugs directly into onboard JST/PH 2.0 battery connector on LilyGO board. | 1 |
| **Audio Amplifier** | MAX98357A I2S DAC Module | Digital-to-analog audio converter for crisp sleep tracks/chimes. Connected via GPIO. | 1 |
| **Speaker** | 8Ω 1W / 2W Micro-Speaker | Compact internal audio driver wired to MAX98357A output terminals. | 1 |
| **Ambient Light** | WS2812B NeoPixel Ring (8 or 12 LEDs) | Addressable RGB lighting ring for task alerts and night-light mode. Controlled via 1 GPIO pin. | 1 |
| **Physical Input** | 6mm Tactile Push Button | External wake-up switch from ESP32 deep sleep / night light override toggle. | 1 |
| **Enclosure** | Custom 3D Printed |~135 mm x 80 mm x 65 mm box housing with translucent top rim diffuser for LED ring. | 1 |

## 📐 Reference Component Dimensions & Clearance Matrix

| Component | Outer Dimensions (L × W × H) | Mount / Cutout Specification | Status |
| :--- | :--- | :--- | :--- |
| **LilyGO T5 4.7" Board** | 121 mm × 67 mm × 12 mm | 4x M2/M2.5 screw bosses matching corner PCB holes | 🟡 Drafted |
| **Touch Screen Active Area** | ~104 mm × 59 mm | Bezel window: 105 mm × 60 mm with 1mm inner bevel | 🟡 Drafted |
| **Li-Po Battery (2000mAh)**| ~50 mm × 34 mm × 10 mm | Lower recessed battery cavity in base chassis | 🟡 Drafted |
| **WS2812B NeoPixel Ring** | Outer Ø: 37 mm, Inner Ø: 23 mm | Circular channel with 1.5mm translucent diffuser inlay | 🟡 Drafted |
| **8Ω 1W Micro-Speaker** | Outer Ø: 28 mm, Height: 5 mm | Rear acoustic isolation pocket + sound grill vents | 🟡 Drafted |
| **USB-C Port (Onboard)** | Located on board edge | Side/rear USB-C port cutout: 12 mm × 7 mm rounded slot | 🟡 Drafted |
| **Tactile Push Button** | 6 mm × 6 mm × 5 mm | 7 mm diameter button cap cutout on top/side wall | 🟡 Drafted |

## 🔌 GPIO Pin Connections (TBC)

### Audio Amplifier (MAX98357A I2S)
| MAX98357A Pin | LilyGO T5 ESP32-S3 Pin | Notes |
| :--- | :--- | :--- |
| **LRC (WS)** | GPIO 14 | I2S Word Select |
| **BCLK** | GPIO 15 | I2S Bit Clock |
| **DIN** | GPIO 13 | I2S Data Input |
| **VIN / VCC** | 5V / VBUS | Power supply |
| **GND** | GND | Common ground |

### Ambient RGB Light & External Wake Button
| Module Pin | LilyGO T5 ESP32-S3 Pin | Notes |
| :--- | :--- | :--- |
| **NeoPixel DIN** | GPIO 21 | Data signal for RGB lighting |
| **NeoPixel VCC** | 3.3V or 5V | Power supply |
| **NeoPixel GND** | GND | Common ground |
| **Push Button** | GPIO 0 (or EXT_WAKE pin) | Configured with internal pull-up resistor |
