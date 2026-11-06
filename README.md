# 🧪 Smell Detector — MQ-136 + ESP8266 + Flutter

An IoT system to **locate the source of a sulfur-based smell** in a room
(e.g. a dead rodent behind a wall) using an MQ-136 gas sensor, an ESP8266,
and a Flutter mobile app.

> ⚠️ **Honest disclaimer:** This is a *smell-strength locator*, not a
> "dead body detector." A single gas sensor cannot identify a body or see
> through walls. It measures sulfur-based gases (H₂S) and helps you narrow
> down where the smell is strongest.

---

## 📸 Screenshots

| Reading Gauge | Compass (mock) | History Chart |
|---------------|----------------|---------------|
| _(add screenshot)_ | _(add screenshot)_ | _(add screenshot)_ |

---

## ✨ Features

- 📊 **Live reading gauge** — raw MQ-136 value (0–4095) with COLD / WARM / HOT status
- 📈 **History chart** — last 60 seconds with baseline & threshold lines
- 🧭 **Compass widget** — shows estimated direction (see [Direction](#-direction-how-it-works))
- 🔔 **Alert logic** — flags when reading crosses the threshold
- 📱 **Flutter UI** — runs on Android, iOS, and web
- 🔌 **HTTP polling** — reads live data from ESP8266 over Wi-Fi

---

## 🗺️ Project Status

| Phase | Description | Status |
|-------|-------------|--------|
| 1 | Flutter mock UI (fake data) | ✅ Done |
| 2 | ESP8266 + MQ-136 over HTTP | ⏳ Planned |
| 3 | Direction via phone compass sweep | ⏳ Planned |
| 4 | 3-sensor triangulation array | 💡 Optional |

---

## 🛠️ Hardware (planned)

| Component | Purpose | Approx. Cost (INR) |
|-----------|---------|--------------------|
| ESP8266 (NodeMCU / Wemos D1 mini) | Microcontroller + Wi-Fi | ₹250 |
| MQ-136 sensor module | Detects H₂S / sulfur gases | ₹1,049 |
| 10k + 20k resistors | Voltage divider (5V → 3.3V) | ₹20 |
| 5V USB power supply | Powers the MQ-136 heater | ₹150 |
| Jumper wires + breadboard | Wiring | ₹150 |
| **Total** | | **~₹1,600** |

> ⚠️ **Power warning:** The MQ-136 heater needs **5V**. Do **not** power it
> from the ESP8266 3.3V pin. Use a separate 5V supply and a voltage divider
> on the analog output.

---

## 🚀 Getting Started

### Prerequisites
- [Flutter SDK](https://flutter.dev/docs/get-started/install) (3.0+)
- Arduino IDE with ESP8266 board support (for Phase 2)

### Run the mock UI

```bash
git clone https://github.com/<your-username>/smell-detector.git
cd smell-detector/flutter_app
flutter pub get
flutter run
