# Goosky S1 - Ethos Setup (V2 ELRS)

![Screenshot 5](doc/{6A63F5D8-1318-40C6-B97C-2D59A8B5D2C5}.png)

**[🇩🇪 Deutsch]**  
Setup für den Goosky S1 in der **V2 ELRS** Variante.

**Features:**
* ✅ ELRS-Setup für Ethos mit externem Funkmodul
* ✅ Empfänger-Setup mit BetaFPV Nano (oder kompatiblen ELRS-Empfängern)
* ✅ Wichtige ELRS-Linkparameter dokumentiert (z. B. 333Hz, 1:8)
* ✅ Drei Modellbild-Farben vorbereitet
* ✅ Screenshot-Sammlung im `doc`-Ordner eingebunden

---

**[🇬🇧 English]**  
Setup for the Goosky S1 **V2 ELRS** variant.

**Features:**
* ✅ ELRS setup for Ethos with external RF module
* ✅ Receiver setup with BetaFPV Nano (or any compatible ELRS receiver)
* ✅ Critical ELRS link parameters documented (e.g. 333Hz, 1:8)
* ✅ Three model bitmap colors prepared
* ✅ Screenshot gallery from the `doc` folder

---

## 🛠 Voraussetzungen / Requirements

### Sender / Radio
* **Ethos-Fernsteuerung:** Für ELRS muss ein **externes ELRS Funkmodul** verwendet werden.
* **Ethos radio:** For ELRS operation, an **external ELRS RF module** is required.

### Empfänger / Receiver
* In dieser Anleitung wird ein kleiner **BetaFPV Nano ELRS** Empfänger verwendet.
* Es kann aber auch jeder andere kompatible ELRS-Empfänger genutzt werden.
* This guide uses a small **BetaFPV Nano ELRS** receiver.
* Any other compatible ELRS receiver can be used as well.

---

## 📶 ELRS Hinweise / ELRS Notes

### Bindung / Binding
* Diese Anleitung beschreibt **nicht** den Bind-Vorgang.
* This guide does **not** cover the binding process.

### Link-Einstellungen / Link Settings
Für eine stabile Verbindung müssen Sender und Empfänger identisch konfiguriert sein.  
For a stable link, transmitter and receiver settings must match.

* **Paketrate / Packet Rate:** z. B. `333Hz`
* **Verhältnis / Telemetry Ratio:** z. B. `1:8`
* Beide Werte müssen auf Sender **und** Empfänger übereinstimmen.
* Both values must match on transmitter **and** receiver.

---

## 🖼 Modellbild-Farben / Model Bitmap Colors

Im Ordner `bitmaps/models` liegen drei vorbereitete Modellbilder für unterschiedliche Farbvarianten.  
The folder `bitmaps/models` contains three prepared model bitmaps for different color variants.

* `GooslyS1-2b.bmp` -> Blau / Blue
* `GooslyS1-2o.bmp` -> Orange
* `GooslyS1-2p.bmp` -> Pink

In Ethos kannst du das gewünschte Bild als Modellbild auswählen.  
In Ethos, select the desired file as model image.

---

## 🎵 Audio-Struktur / Audio Structure

Vorhandene Struktur:
* `audio/de/default`
* `audio/en/default`

Lege hier deine Sprachansagen für Schalterzustände, Motorstatus und Rettung ab.  
Place voice prompts for switch states, motor status, and rescue here.

---

## 📡 Kanalbelegung / Channel Mapping

Die Mischerbelegung im Modell ist wie folgt aufgebaut:  
The mixer channel mapping in this model is set up as follows:

| CH | Funktion | Quelle |
| :--- | :--- | :--- |
| **1** | Roll | Roll |
| **2** | Nick | Nick |
| **3** | Gas / Throttle | Maximum |
| **4** | Heck / Rudder | Heck |
| **5** | Rettung / Rescue | Rettung |
| **6** | Pitch | Pitch |

![Kanalbelegung Mischer](doc/{AABF09B9-8345-443E-A42C-A8CBECED3D99}.png)

---

## ⚙️ Gaswerte einstellen / Adjusting Throttle Values

Die Gaswerte werden direkt im Mischer auf **Kanal 3 (Gas)** über die Gewichtungen pro Aktion gesetzt.  
Throttle values are set directly in the **Channel 3 (Throttle)** mixer via action weights.

### Vorgehen / Procedure
* Öffne **Modell -> Mischer -> Gas (CH3)**.
* Setze **Quelle / Source** auf `Maximum`.
* Nutze einen freien Mischer und hinterlege die gewünschten Gewichte pro Aktion.
* Passe die Prozentwerte der einzelnen Aktionen an die gewünschte Kopfdrehzahl an.

Damit kannst du deine Headspeed-Stufen schnell anpassen, ohne die Kanalstruktur zu ändern.  
This lets you tune head speed levels quickly without changing channel structure.

---

## 🖼 Screenshots / Screenshots

Dokumentierte Ansichten aus dem `doc`-Ordner:  
Documented views from the `doc` folder:

![Screenshot 1](doc/{542EC4D8-9F12-4296-91EC-2023D272108A}.png)
![Screenshot 2](doc/{8D0DB1CC-DF34-4564-A814-33A3FF714076}.png)
![Screenshot 3](doc/{DFD645BF-95D4-4D49-90D7-F1443040E3D9}.png)
![Screenshot 4](doc/{78B895C0-24A1-4F29-8CEF-4E81F38162BD}.png)
![Screenshot 5](doc/{AABF09B9-8345-443E-A42C-A8CBECED3D99}.png)

![Screenshot 6](doc/{9E8B4D1E-C3EA-429B-821E-A7E20E072C45}.png)
![Screenshot 7](doc/{0B110FE2-820B-4938-A771-E8B18A50798E}.png)

---

## ⚠️ Hinweise / Notes

* Prüfe nach jedem Modellimport die ELRS-Linkparameter auf beiden Seiten (Sender/Empfänger).
* Übernimm die Mischerwerte immer 1:1 aus dem finalen Modellstand.
