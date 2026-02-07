# 🚁 RC Transmitter Configurations / RC Sender Konfigurationen

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

**[🇩🇪 Deutsch]**
Dieses Repository dient als zentraler Speicherort für vorprogrammierte Modell-Setups verschiedener RC-Sender-Systeme (z.B. FrSky Ethos, EdgeTX, OpenTX). Das Ziel ist es, komplexe Programmierungen für Helikopter und Flächenmodelle inklusive der zugehörigen Modellbilder bereitzustellen.

**[🇬🇧 English]**
This repository serves as a central storage for pre-programmed model setups for various RC transmitter systems (e.g., FrSky Ethos, EdgeTX, OpenTX). The goal is to share complex programming for helicopters and fixed-wing aircraft, including the corresponding model images.

---

## ⚠️ Wichtiger Hinweis zur Sprache / Important Language Note

**🇩🇪**
Obwohl diese Dokumentation zweisprachig ist, sind die **Modell-Dateien selbst auf Deutsch programmiert**.
Das bedeutet, dass interne Bezeichnungen wie Flugphasen, Mischer oder Logische Schalter deutsche Namen tragen.
* *Beispiel:* Eine Flugphase heißt `FP_Schweben` anstatt `FM_Hover`.
* *Beispiel:* Ein Mischer heißt `Gas` anstatt `Throttle`.

**🇬🇧**
Although this documentation is bilingual, the **model files themselves are programmed in German**.
This means internal naming conventions for Flight Modes, Mixers, or Logical Switches use German terms.
* *Example:* A Flight Phase is named `FP_Schweben` instead of `FM_Hover`.
* *Example:* A Mixer is named `Gas` instead of `Throttle`.

---

## 📂 Struktur / Structure

Die Ordnerstruktur innerhalb eines Modells spiegelt die **Verzeichnisstruktur der SD-Karte** wider.
The folder structure within a specific model mirrors the **SD card directory structure**.

```text
rc-transmitter-configs/
├── Ethos/                   <-- Betriebssystem / OS
│   ├── Goosky/              <-- Hersteller / Manufacturer
│   │   ├── S1/              <-- Modell / Model
│   │   │   ├── bitmaps/     <-- Bilder Ordner (SD-Struktur)
│   │   │   │   └── models/
│   │   │   │       └── s1.png
│   │   │   ├── models/      <-- Modelldatei Ordner (SD-Struktur)
│   │   │   │   └── s1.bin
│   │   │   └── README.md    <-- Anleitung & Schalter / Manual & Switches
│   │   └── ...
├── EdgeTX/
└── ...
