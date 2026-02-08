# 🚁 RC Transmitter Configurations / RC Sender Konfigurationen

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

**[🇩🇪 Deutsch]**
Dieses Repository dient als zentraler Speicherort für vorprogrammierte Modell-Setups verschiedener RC-Sender-Systeme (z.B. FrSky Ethos, EdgeTX, OpenTX). Das Ziel ist es, komplexe Programmierungen für Helikopter und Flächenmodelle inklusive der zugehörigen Modellbilder bereitzustellen.

**[🇬🇧 English]**
This repository serves as a central storage for pre-programmed model setups for various RC transmitter systems (e.g., FrSky Ethos, EdgeTX, OpenTX). The goal is to share complex programming for helicopters and fixed-wing aircraft, including the corresponding model images.

---

## ⚠️ Wichtiger Hinweis zur Sprache / Important Language Note

**[🇩🇪 Deutsch]**
Obwohl diese Dokumentation zweisprachig ist, sind die **Modell-Dateien selbst auf Deutsch programmiert**.
Das bedeutet, dass interne Bezeichnungen wie Flugphasen, Mischer oder Logische Schalter deutsche Namen tragen.
* *Beispiel:* Eine Flugphase heißt `FP_Schweben` anstatt `FM_Hover`.
* *Beispiel:* Ein Mischer heißt `Gas` anstatt `Throttle`.

**[🇬🇧 English]**
Although this documentation is bilingual, the **model files themselves are programmed in German**.
This means internal naming conventions for Flight Modes, Mixers, or Logical Switches use German terms.
* *Example:* A Flight Phase is named `FP_Schweben` instead of `FM_Hover`.
* *Example:* A Mixer is named `Gas` instead of `Throttle`.

---

## 📂 Struktur / Structure

Die Ordnerstruktur innerhalb eines Modells spiegelt die **Verzeichnisstruktur der SD-Karte** wider, um die Installation zu vereinfachen.

The folder structure within a specific model mirrors the **SD card directory structure** to simplify installation.

```text
rc-transmitter-configs/
├── Ethos/                        <-- Betriebssystem / OS
|   └── Helicopter/              <-- Modelltyp / Model Type
│       ├── Goosky/              <-- Hersteller / Manufacturer
│       │   ├── S1/              <-- Modell / Model
│       │   │   ├── bitmaps/     <-- Bilder Ordner (SD-Struktur)
│       │   │   │   └── models/
│       │   │   │       └── s1.png
│       │   │   ├── models/      <-- Modelldatei Ordner (SD-Struktur)
│       │   │   │   └── s1.bin
│       │   │   └── README.md    <-- Anleitung & Schalter / Manual & Switches
│       │   └── ...
├── EdgeTX/
└── ...
```

## 🚀 Erste Schritte / Getting Started

### **[🇩🇪 Deutsch]** Installation (Beispiel: Ethos)
1.  Navigiere in den Ordner des gewünschten Modells (z.B. `Ethos/Goosky/S1`).
2.  Lies die dortige `README.md` für spezifische Schalterbelegungen und Voraussetzungen.
3.  Lade die Ordner `models` und `bitmaps` herunter (oder den gesamten Modellordner).
4.  Kopiere den Inhalt (die Ordner `models` und `bitmaps`) direkt in das **Hauptverzeichnis (Root)** deiner Sender-SD-Karte.
    * *Hinweis:* Wenn dein Betriebssystem fragt, integriere die Ordner in die bestehenden Verzeichnisse ("Zusammenführen").
5.  **Sicherheit:** Entferne vor dem ersten Test immer die Rotorblätter/Propeller! Prüfe die Laufrichtung der Taumelscheibe und des Heckrotors.

### **[🇬🇧 English]** Installation (Example: Ethos)
1.  Navigate to the folder of the desired model (e.g., `Ethos/Goosky/S1`).
2.  Read the local `README.md` for specific switch assignments and requirements.
3.  Download the folders `models` and `bitmaps` (or the entire model folder).
4.  Copy the content (the folders `models` and `bitmaps`) directly to the **root directory** of your transmitter's SD card.
    * *Note:* If prompted by your OS, merge the folders with the existing ones.
5.  **Safety:** Always remove rotor blades/propellers before the first test! Check the direction of the swashplate and tail rotor.

---

## 🤝 Contributing

**[🇩🇪 Deutsch]**
Du hast eine Optimierung für den Goosky S1 oder ein Setup für ein anderes Modell? Pull Requests sind willkommen!

* Bitte achte darauf, die Dateistruktur (`bitmaps`/`models`) beizubehalten.
* Benenne logische Schalter sinnvoll (gerne auf Deutsch).
* Füge eine kurze `README.md` mit den Schalterbelegungen hinzu.

**[🇬🇧 English]**
Do you have an optimization for the Goosky S1 or a setup for another model? Pull Requests are welcome!

* Please ensure you maintain the file structure (`bitmaps`/`models`).
* Name logical switches meaningfully (German naming is fine).
* Add a short `README.md` explaining the switch assignments.

---

## ⚖️ Disclaimer / Haftungsausschluss

**[🇩🇪 Deutsch]**
Benutzung auf eigene Gefahr. Der Autor haftet nicht für Schäden, die durch die Nutzung dieser Konfigurationen entstehen. Überprüfe die Einstellungen immer auf der Werkbank, bevor du fliegst. Dies ist ein Community-Projekt und steht in keiner Verbindung zu den Herstellern der RC-Systeme.

**[🇬🇧 English]**
Use at your own risk. The author is not responsible for any damage caused by using these configurations. Always verify setups on the bench before flying. This is a community project and is not affiliated with the manufacturers of the RC systems.
