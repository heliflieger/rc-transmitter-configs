# Goosky S1 - Ethos Setup

![Goosky S1 Dashboard](doc/dashboard.png)

**[🇩🇪 Deutsch]**
Ein Setup für den Goosky S1.  
**Besonderheit:** Dieses Profil ist auf maximale Benutzerfreundlichkeit ausgelegt. Alle Schalterzuordnungen werden zentral über **Logische Schalter** gesteuert. Du musst keine Mischer bearbeiten, um Schalter zu ändern!

**Features:**
* ✅ **Smart Flight Counter:** Zählt Flüge nur, wenn Motor AN ist **UND** eine Verbindung zum Heli besteht (RSSI > 35dB).
* ✅ **Easy Customization:** Ändere Schalter zentral in den Logischen Schaltern.
* ✅ **Double Safety:** Motor-Sicherung verknüpft zwei Schalterpositionen.
* ✅ **Beginner Friendly:** "Hover"-Modus mit reduzierten Ausschlägen (60%).

---

**[🇬🇧 English]**
An setup for the Goosky S1.  
**Special Feature:** Designed for maximum ease of use. All switch assignments are routed through **Logical Switches**. You don't need to touch mixers to change switches!

**Features:**
* ✅ **Smart Flight Counter:** Only counts flights when Motor is ON **AND** connection is active (RSSI > 35dB).
* ✅ **Easy Customization:** Change switches centrally in the Logical Switches menu.
* ✅ **Double Safety:** Throttle cut logic links two switch positions.
* ✅ **Beginner Friendly:** "Hover" mode with reduced rates (60%).

---

## 🛠 Voraussetzungen & Verkabelung / Requirements & Wiring

Damit dieses Setup funktioniert, wird folgende Hardware empfohlen:  
To make this setup work, the following hardware is recommended:

### Empfänger / Receiver
* **Modell:** FrSky **Archer Plus RS Mini** (oder vergleichbarer kleiner S.BUS Empfänger).
* **Protokoll:** ACCESS oder ACCST D16.
* **Verbindung:** S.BUS Port am Empfänger -> S.BUS Port am Goosky Flight Controller.

### Verkabelung / Wiring Diagram
Bitte achte auf die korrekte Polung am Flight Controller!  
Für den SBUS-Anschluss wird das blaue Kabel vom Archer nicht benötigt und kann somit entfernt werden.  
Please pay attention to the correct polarity on the flight controller!  
The blue cable from the Archer is not required for the SBUS connection and can therefore be removed.  

![Verkabelung / Wiring Schema](doc/wiring.jpg)

> **Hinweis:** Der Archer Plus RS Mini ist klein genug, um direkt im Rahmen des S1 Platz zu finden.  
> **Note:** The Archer Plus RS Mini is small enough to fit directly inside the S1 frame.

---

## 🛠 Anpassung der Schalter / How to Change Switches

**Das Wichtigste zuerst / First things first:**  
Du musst nicht in die Mischer gehen. Gehe einfach zu **Modell -> Logische Schalter**.  
You don't need to edit Mixers. Just go to **Model -> Logical Switches**.

| LS # | Funktion / Function | Standard / Default | Ändern / How to change |
| :--- | :--- | :--- | :--- |
| **LS1** | Flugphase: Schweben (Hover) | `SC` (oben/-100%) | Ändere Quelle `SC` auf deinen Wunschschalter. |
| **LS2** | Flugphase: Kunstflug (Soft 3D) | `SC` (mitte/0%) | Ändere Quelle `SC` (passend zu LS1). |
| **LS3** | Flugphase: 3D (Hard 3D) | `SC` (unten/+100%) | Ändere Quelle `SC` (passend zu LS1). |
| **LS4** | Rettung / Rescue | `SF` (unten/100%) | Ändere Quelle `SF` (z.B. auf einen Taster). |
| **LS5** | Motor Scharf / Arm | `SE` (unten/>50%) | Ändere Quelle `SE`. |

---

## 🧠 Die Logik im Detail / Logic Deep Dive

Hier ist eine Erklärung der vorprogrammierten Logik, falls du verstehen willst, wie das System arbeitet.  
Here is an explanation of the pre-programmed logic if you want to understand how the system works.

### 1. Flugphasen (Flight Modes)
* Gesteuert über **LS1, LS2, LS3**.
* **Hover (LS1):** Nutzt Dual-Rates von 60% auf Roll/Nick für ruhiges Schweben.
* **Kunstflug/3D (LS2/LS3):** Nutzt 100% Ausschläge.

### 2. Sicherheits-Logik (Safety) - LS6
Ein spezieller Schalter namens `Throttle cut` sorgt für Sicherheit.
* Der Motor ist **AUS**, wenn diese Logik aktiv ist.
* **Bedingung:** `SE` (unten) **UND** `SB` (oben).
* *Vorteil:* Du kannst eine komplexe Entsperr-Sequenz bauen, indem du hier die Bedingungen änderst.

### 3. Intelligenter Flugzähler (Smart Counter) - LS8 & VAR1
Der Zähler ist extrem präzise. Er erhöht den Wert "Flüge" nur, wenn:
1.  **LS5 (Motor an)** aktiv ist.
2.  **UND LS7 (Link Aktiv)** aktiv ist (RSSI > 35dB).
3.  **Der Motor mindestens 30s läuft.**

* Das verhindert, dass Tests auf der Werkbank (ohne eingeschalteten Heli) den Zähler hochtreiben.
* Realisiert über einen "Berechneten Sensor", der die Variable `VAR1` nutzt.

---

## 📡 Kanalbelegung / Channel Mapping

| CH | Funktion | Mischer Name | Details |
| :--- | :--- | :--- | :--- |
| **1** | Roll | Roll | 60% in Hover, sonst 100% |
| **2** | Nick | Nick | 60% in Hover, sonst 100% |
| **3** | Gas / Throttle | Gas | Kurven: `Gas_Hover`, `Gas_Kunstflug`, `Gas_3D` |
| **4** | Heck / Rudder | Heck | Standard 100% |
| **5** | Rettung / Rescue | Rettung | Wird durch LS4 (`SF`) auf +100% gesetzt |
| **6** | Pitch | Pitch | Linear -100 bis +100 |

---

## 🎵 Spezialfunktionen (Audio)

Folgende Ansagen sind vorkonfiguriert:
* **SF1-SF3:** Ansage der Flugphasen (Normal, Kunstflug, 3D).
* **SF4-SF5:** Motor An / Motor Aus.
* **SF6:** Stabilize/Rettung Ansage.
* *Hinweis:* Stelle sicher, dass du entsprechende Sounddateien auf deiner SD-Karte hast, oder weise sie neu zu.

---

## ⚠️ Wichtige Hinweise / Important Notes

**[🇩🇪]**
* **Gaskurven:** Die Kurven `Gas_Hover`, `Gas_Kunstflug` und `Gas_3D` sind als Platzhalter (Flat Curves) angelegt. Bitte passe die Prozentwerte an deine gewünschte Kopfdrehzahl an!
* **Rettung:** Prüfe am Boden trocken, ob bei Betätigung von `SF` (oder deinem gewählten Schalter) der Kanal 5 ausschlägt.

**[🇬🇧]**
* **Throttle Curves:** The curves `Gas_Hover`, `Gas_Kunstflug`, and `Gas_3D` are set as placeholders (flat curves). Please adjust the percentage values to your desired head speed!
* **Rescue:** Dry test on the ground to ensure Channel 5 responds when `SF` (or your chosen switch) is activated.