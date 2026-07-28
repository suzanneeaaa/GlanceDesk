# Product Roadmap & Development Milestones: GlanceDesk

> **Current Focus:** Phase 1 — CAD & Chassis Modeling  
> **Target Board:** LilyGO T5 4.7" E-Paper V2.3 (ESP32-S3 Touch)

---

## 🚩 Phase 1: CAD Design & Chassis Prototyping (CURRENT PHASE)

- [ ] **1.1 CAD Clearance Setup:** Import/sketch baseline component dimensions into Fusion 360 (LilyGO 121×67×12mm board, 2000mAh Li-Po, 37mm LED ring, 28mm micro-speaker).
- [ ] **1.2 Angled Shell Modeling:** Create 2-part desktop wedge shell with 15°–25° screen viewing angle.
- [ ] **1.3 Ports & Acoustic Isolation:** Cut out side USB-C access slot, top button recess, and rear speaker isolation chamber with sound grill.
- [ ] **1.4 Light Diffuser Channel:** Model 1.5mm translucent PETG diffuser ring overlay for the WS2812B NeoPixel ring.
- [ ] **1.5 Prototype 3D Print (v1):** Print housing on FDM printer (PLA/PETG) and test physical fit of board, screen bezel, and screw bosses.

---

## 🚩 Phase 2: Hardware Assembly & Bench Testing

- [ ] **2.1 Power Wiring:** Solder 3.7V Li-Po battery to JST PH 2.0 connector and verify onboard LilyGO TP4056 charging IC.
- [ ] **2.2 Audio Integration:** Solder MAX98357A I2S DAC module and 8Ω 1W micro-speaker to ESP32-S3 expansion GPIO pins (GPIO 13, 14, 15).
- [ ] **2.3 Ambient Lighting:** Connect WS2812B NeoPixel RGB ring to GPIO 21 and test power draw.
- [ ] **2.4 Physical Input:** Wire tactile push button to GPIO 0 / EXT_WAKE pin for deep sleep wake-up.
- [ ] **2.5 Final Fitting:** Mount all hardware inside 3D printed chassis and secure with M2.5 screws.

---

## 🚩 Phase 3: Core Firmware Development (Arduino Framework)

- [ ] **3.1 Display Pipeline:** Setup `LilyGo-EPD47` driver in Arduino IDE to render grayscale text and UI widget frames.
- [ ] **3.2 Wi-Fi & API Fetcher:** Write asynchronous HTTP client to pull live transport data (Singapore LTA DataMall API) and local weather JSON.
- [ ] **3.3 Touch Navigation:** Implement capacitive touch screen swipe gestures (`FT6336U` driver) to toggle between Morning Dashboard and Night Mode.
- [ ] **3.4 Deep Sleep Routine:** Configure ESP32-S3 RTC sleep cycles to refresh e-paper every 60 seconds with sub-1mA standby current.
- [ ] **3.5 Audio & Light Engine:** Add sleep music audio playback via I2S and set up auto-off night light timers on NeoPixel ring.

---

## 🚩 Phase 4: Developer SDK & Ecosystem

- [ ] **4.1 Local HTTP Server:** Enable lightweight REST endpoint / WebSockets on ESP32-S3 to accept local webhooks.
- [ ] **4.2 Python SDK (`glancedesk-sdk`):** Publish Python package to pipe terminal status, AI agent progress, and token metrics to GlanceDesk over local Wi-Fi.
- [ ] **4.3 Web Configurator:** Host a local setup page on GlanceDesk for setting Wi-Fi credentials, bus stop codes, and display themes.
