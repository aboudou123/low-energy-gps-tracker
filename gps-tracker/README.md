

# Projekt: Tier-GPS-Tracker (Mantro GmbH)

---

## Motivation

Die Firma **Mantro GmbH** beabsichtigt die Entwicklung eines zuverlässigen GPS-Trackers für Tiere (beispielweise für den Einsatz bei Jagdhunden).

Das Projekt konzentriert sich auf die Symbiose zweier kritischer Erfolgskriterien:

### 1. Energieeffizienz

Der mobile Betrieb stellt hohe Anforderungen an das Energiemanagement.

* **Ziel:** Ein minimaler Energieverbrauch.
  
* **Fokus:** Besonders in Ruhephasen, in denen der Tracker nicht aktiv benötigt wird, muss die Laufzeit maximiert werden.

### 2. Zuverlässigkeit & Netzabdeckung

Die Funktionalität muss auch unter schwierigen Bedingungen sichergestellt sein.

* **Herausforderung:** Einsatz in Zielgebieten mit unzureichender stationärer Mobilfunkabdeckung.

* **Lösung:** Gewährleistung der Standortermittlung und Datenübertragung trotz schwacher Infrastruktur.

---
## Lesons

**Low-Energy GPS Tracker**

Table of Contents

• Research Objective

• What is GPS?

• Primary Functions

• Literature Review

• Problem Statement

• Implementation

  - Wireless Network
  - Wearable Sensors
  - Cloud Analysis Services

    
• System Architecture

• Results and Discussions

• Comparison of Communication Technologies

  - LoRaWAN vs. NB-IoT

• LPWAN Basics

• References

**Research Objective**

• Explain what GPS and other tracking technologies are.

• Describe the structure and functionality of the GPS system.

• Research the technologies involved in developing GPS tracking systems.

• Compare various IoT technologies: Low-Power Wide-Area Network (LPWA).

# What is GPS?

Global Positioning System (GPS) is a network of satellites that orbit the Earth, providing positional information about their locations.

## Segments of GPS

Space Segment: The satellites themselves.

Ground Segment: The infrastructure that controls the satellites.

User Segment: The devices that receive GPS signals.

## Primary Functions

• Positioning and coordinates.

• Measuring distance and direction between waypoints.

• Progress reporting for travel.

• Accurate timekeeping.

## Literature Review

• IBM Tracking Solution: Investigates advanced tracking methodologies and their applications.

## Problem Statement

Poaching threatens thousands of endangered species annually.

Research indicates that animal movement varies based on perceived threats. 

The aim is to develop an early warning system that alerts rangers to poachers' presence using a long-range IoT tracking system with LoRaWAN.

## Implementation

**Wireless Network**

• Utilizes LoRaWAN for low-energy communication.

**Wearable Sensors**

• Integrates GPS modules (e.g., NEO-6M) for tracking.

**Cloud Analysis Services**

• Employs cloud-based services for data analysis and reporting.

## System Architecture


<img width="811" height="638" alt="image" src="https://github.com/user-attachments/assets/a0624515-ee5b-47b2-8db8-d0e45d604b4b" />



### Hardware Components

• Arduino Mega

• Dragino LoRa/GPS Shield (868 MHz)

• SIM808 Expansion Shield

• GPS Antennas

• External Power Supply

• Wiring and SIM Card
  
`yaml
Arduino IDE
version: 1.8.7
`


## Software

• The Arduino Mega 2560 is a microcontroller with:
  - 54 digital I/O pins
  - 16 analog inputs
  - 4 UARTs (hardware serial ports)



## Hardware:

 <img width="1055" height="607" alt="image" src="https://github.com/user-attachments/assets/740245d0-79df-456f-b3a2-3526102a7742" />

 <img width="1057" height="591" alt="image" src="https://github.com/user-attachments/assets/8ed95525-4e68-46b3-9c25-6d5132c036c8" />

 
 <img width="1077" height="557" alt="image" src="https://github.com/user-attachments/assets/6272548a-444c-4e0a-b969-842d04fc6931" />


<img width="1077" height="579" alt="image" src="https://github.com/user-attachments/assets/533cb7b6-5e62-43b7-8ce3-fb82938a3fa9" />

<img width="1086" height="573" alt="image" src="https://github.com/user-attachments/assets/2d920a00-0cc0-4eb2-aea9-e6916810b904" />

<img width="986" height="532" alt="image" src="https://github.com/user-attachments/assets/13d06ecd-ed67-4a29-8aed-4fba44a22bc0" />

<img width="1091" height="582" alt="image" src="https://github.com/user-attachments/assets/43542ec4-4daf-4c1b-89ff-d23ed55f5b3f" />

<img width="1088" height="623" alt="image" src="https://github.com/user-attachments/assets/57d083fd-9612-430f-8b5c-0df6732655cb" />


<img width="1125" height="608" alt="image" src="https://github.com/user-attachments/assets/9db31651-5b32-47e8-bfa8-e37fa37cfc74" />


<img width="1014" height="592" alt="image" src="https://github.com/user-attachments/assets/80095c74-6b99-4ccb-be99-93d4c1c71aed" />


<img width="1049" height="636" alt="image" src="https://github.com/user-attachments/assets/8410c0a6-0e12-43ec-9b54-a14233aa506f" />






Results and Discussions
The SD card module has six pins notable for its functions:

| Pin Name | Description                                    | Arduino Pin  |
|----------|------------------------------------------------|---------------|
| CS       | Chip Select - connects to D5                   | D5            |
| SCK      | Synchronizes data transfer - connects to D13   | D13           |
| MOSI     | Data Transfer (Master Out Slave In) - connects to D11 | D11   |
| MISO     | Data Transfer (Master In Slave Out) - connects to D12  | D12  |
| VCC      | Power Supply - connects to 5V                  | 5V            |
| GND      | Ground - connects to GND                       | GND           |

Discussion Points
• Utilizing the Dragino YUN Shield has proven cumbersome; data resets upon rebooting the LoRa gateway. An alternative is to implement the SD card module for data recording.
• Environmental influence on radio frequency coverage has been analyzed, suggesting the necessity for higher-gain antennas to enhance performance.

Comparison of Communication Technologies
LoRaWAN vs. NB-IoT
• Advantages:
  - Increased data transmission rates with 5G (up to 10 Gbps).
  - Lower power consumption with LoRaWAN compared to NB-IoT.
  
| Technology   | Advantages                                             | Disadvantages                                        |
|--------------|--------------------------------------------------------|-----------------------------------------------------|
| NB-IoT   | Better connection quality, scalability, and security.  | Higher operational costs due to cellular dependency. |
| LoRaWAN  | Cost-effective, no SIM cards required, private networks possible.        | Infrastructure development is ongoing.              |

LPWAN Basics
Low Power Wide Area Networks (LPWAN) are designed for IoT applications, addressing the limitations of cellular technologies and short-range networks in terms of cost and power consumption.

``


=================================
# PROJEKT UMSEZUNG II
===================================

---

## Phase 2: Implementierung mit SIM-Karte

In dieser Phase liegt der Schwerpunkt auf der Konnektivität und der Datenübertragung unter realen Bedingungen. Um die Anforderungen aus der Motivation (Energieeffizienz vs. Erreichbarkeit) zu erfüllen, werden folgende Aspekte umgesetzt:

### 1. Hardware & Konnektivität

* **SIM-Auswahl:** Einsatz von M2M-SIM-Karten (Multi-Netz-Fähigkeit), um bei Jagdeinsätzen automatisch das stärkste verfügbare Mobilfunknetz zu wählen.
* **Modul-Wahl:** Verwendung von stromsparenden Funktechnologien wie **LTE-M** (Cat-M1) oder **NB-IoT**, die speziell für hohe Reichweite bei geringem Energiebedarf entwickelt wurden.

### 2. Optimierung des Datenverbrauchs

Um die Akkulaufzeit trotz aktiver SIM-Verbindung zu maximieren, werden folgende Protokolle implementiert:

* **UDP/MQTT-Integration:** Schlanke Datenprotokolle statt schwerfälligem HTTP, um die Sendezeit des Funkmoduls zu minimieren.
* **Intervall-Steuerung:** Dynamische Anpassung der Sendeintervalle (z. B. 30 Sekunden bei Bewegung, 1 Stunde im Ruhemodus).

### 3. Fallback-Strategien

Da die Mobilfunkabdeckung laut Aufgabenstellung lückenhaft sein kann:

* **Lokaler Cache:** Speicherung der GPS-Koordinaten auf dem internen Speicher, falls kein Netz verfügbar ist.
* **Burst-Upload:** Sobald wieder eine Verbindung besteht, werden alle zwischengespeicherten Datenpakete gesammelt übertragen.

### Technische Anforderungen (Tabelle)

| Feature | Spezifikation | Zielsetzung |
| --- | --- | --- |
| **Netzstandard** | LTE-M / NB-IoT | Hohe Gebäudedurchdringung & Reichweite |
| **Roaming** | National Roaming | Beste Abdeckung im Wald/Jagdgebiet |
| **Power Mode** | PSM (Power Saving Mode) | Standby-Stromverbrauch reduzieren |

---

**Arduino-Client-Schnittstellenunterstützung**

Diese Bibliothek lässt sich einfach in viele Sketches integrieren, die **Ethernet** oder **WiFi** verwenden.
Beispiele für **PubSubClient (MQTT)**, **Blynk**, **HTTP Client** und **File Download** sind enthalten.

---

## **TinyGSM ist klein**

Das vollständige **WebClient**-Beispiel für **Arduino Uno** (über **Software Serial**) benötigt nur sehr wenige Ressourcen:

```
Sketch uses 15022 bytes (46%) of program storage space. Maximum is 32256 bytes.
Global variables use 574 bytes (28%) of dynamic memory, leaving 1474 bytes for local variables. Maximum is 2048 bytes.
```

Die **Arduino GSM library** verwendet in einem vergleichbaren Szenario 15868 Bytes (49 %) Flash und 1113 Bytes (54 %) RAM.
**TinyGSM** ruft Daten außerdem schonend vom Modem ab (wann immer möglich) und kann daher mit sehr wenig RAM arbeiten.
So haben Sie mehr Speicherplatz für Ihre Experimente.

---

## **Unterstützte Modems**

• SIMCom SIM800-Serie (SIM800A, SIM800C, SIM800L, SIM800H, SIM808, SIM868)
• SIMCom SIM900-Serie (SIM900A, SIM900D, SIM908, SIM968)
• SIMCom WCDMA/HSPA/HSPA+ Module (SIM5360, SIM5320, SIM5300E, SIM5300E/A)
• SIMCom LTE Module (SIM7100E, SIM7500E, SIM7500A, SIM7600C, SIM7600E)
• SIMCom SIM7000E/A/G CAT-M1/NB-IoT Modul
• SIMCom SIM7070/SIM7080/SIM7090 CAT-M1/NB-IoT Modul
• SIMCom A7672X CAT-M1 Modul
• AI-Thinker A6, A6C, A7, A20
• ESP8266/ESP32 (AT-Befehlsschnittstelle, ähnlich GSM-Modems)
• Digi XBee WiFi und Cellular (über XBee-Kommandomodus)
• Neoway M590
• u-blox 2G, 3G, 4G und LTE Cat1 Mobilfunkmodems
• u-blox LTE-M/NB-IoT Modems
• Sequans Monarch LTE Cat M1/NB1 (VZM20Q)
• Quectel BG96
• Quectel BG95
• Quectel M95
• Quectel MC60 (alpha)

---

## **Unterstützte Boards/Module**

• EnviroDIY LTE Bee, WiFi Bee
• Arduino MKR GSM 1400
• Sodaq GPRSbee, uBee
• Microduino GSM
• Adafruit FONA Mini Cellular GSM Breakout, 800/808 Shield, FONA 3G
• Industruino GSM
• Dragino NB-IoT Bee
• Digi XBee S6B, XBee LTE Cat 1, XBee3 LTE Cat 1, XBee3 CatM
• Nimbelink Skywire/Airgain NL-SW-LTE-QBG96, NL-SW-LTE-QBG95
• RAK WisLTE (alpha)

---

# **Funktionen**

## **Datenverbindungen**

• TCP (HTTP, MQTT, Blynk, …)
 - ALLE Module unterstützen TCP-Verbindungen
 - Die meisten Module unterstützen mehrere gleichzeitige Verbindungen (siehe jeweilige Limits)

• UDP
 - Derzeit von keinem Modul unterstützt

• SSL/TLS (HTTPS)
 - Unterstützt auf bestimmten Modellen/Firmwareständen
 - Wie TCP meist mehrere gleichzeitige Verbindungen möglich
 - TCP- und SSL-Verbindungen können kombiniert werden

---

## **USSD**

• Senden von USSD-Anfragen und Dekodieren von 7-, 8- und 16-Bit-Antworten
 - Unterstützt auf den meisten Mobilfunkmodems
 - Nicht möglich auf XBee und ESP8266

---

## **SMS**

• Nur Senden von SMS wird unterstützt, kein Empfangen
 - Unterstützt auf allen Mobilfunkmodulen

---

## **Sprachanrufe**

• Unterstützt auf ausgewählten Modems
• Funktionen:
 - Wählen, Auflegen
 - DTMF senden

---

## **Standort**

• GPS/GNSS auf unterstützten Modellen
• GSM-Standortdienst verfügbar auf ausgewählten Modems

---

# **Erste Schritte**

## **Erste Schritte**

1. Mit Ihrem Telefon:
    - PIN-Code der SIM deaktivieren
    - Guthaben prüfen
    - APN, Benutzer und Passwort prüfen und Internetverbindung sicherstellen
2. SIM-Karte korrekt einsetzen
3. GSM-Antenne fest anschließen
4. Stabile Stromversorgung mit mindestens 2 A sicherstellen
5. Serielle Verbindung prüfen (Hardware Serial empfohlen)
    Senden Sie einen **`AT`**-Befehl mit dem Beispielsketch
6. Testen Sie das **WebClient**-Beispiel

---

# **Eigenen Code schreiben**

Der allgemeine Ablauf Ihres Codes sollte sein:

• Modul definieren (genau eines auswählen)
 - z. B. **`#define TINYGSMMODEMSIM800`**

• **TinyGSM** einbinden
 - **`#include <TinyGsmClient.h>`**

• TinyGSM-Modeminstanz erstellen
 - **`TinyGsm modem(SerialAT);`**

• Eine oder mehrere Client-Instanzen erstellen
 - **`TinyGsmClient client(modem);`**
 - oder **`TinyGsmClientSecure client(modem);`**

• Serielle Kommunikation starten, Pins konfigurieren, Modul initialisieren
• Auf Bereitschaft warten
• Modem initialisieren
 - **`modem.init()`** oder **`modem.restart()`**

• SIM ggf. entsperren
 - **`modem.simUnlock(GSMPIN)`**

• Netzwerkverbindung aufbauen
 - **`modem.waitForNetwork(600000L)`**

• Datenverbindung herstellen
 - **`modem.gprsConnect(apn, gprsUser, gprsPass)`**

• TCP/SSL-Client verbinden
 **`client.connect(server, port)`**

• Daten senden

---

# **Wie funktioniert das?**

Viele GSM-, WiFi- und Funkmodule werden über **AT-Befehle** per serieller Schnittstelle gesteuert.
**TinyGSM** weiß, welche Befehle gesendet werden müssen, verarbeitet die Antworten und kapselt dies in der standardisierten **Arduino Client**-Schnittstelle.

Diese Bibliothek arbeitet blockierend.
Bestimmte Funktionen können Ihren Code für längere Zeit blockieren, während auf Antworten des Moduls gewartet wird.

Die Bibliothek unterstützt keine Hardware- oder Pin-Steuerungen.
Falls Sie Ihr Modul über GPIOs ein- oder ausschalten oder zurücksetzen möchten, müssen Sie dies selbst implementieren.

---

# **API-Referenz**

Für GPRS-Datenströme stellt die Bibliothek die Standard-**Arduino Client**-Schnittstelle bereit.
Weitere Funktionen finden Sie im Beispielsketch.

---

# **Fehlerbehebung**

## **Stabile Daten- und Stromversorgung sicherstellen**

Viele Module benötigen bis zu 2 A zum Verbinden mit dem Netzwerk – viermal so viel wie ein Standard-USB-Port liefert.
Eine bessere Stromversorgung behebt häufig Stabilitätsprobleme.

• Kabel kurz halten
• Verbindungen löten
• Abstand zu Störquellen einhalten
• Stromversorgung prüfen

---

## **Baudraten**

Viele Module unterstützen Auto-Baud.
**TinyGSM** bietet **`TinyGsmAutoBaud(...)`**, dies sollte jedoch nicht im Produktionscode verwendet werden.
Nach erfolgreicher Kommunikation die Baudrate mit **`setBaud(#)`** fest einstellen.

---

## **Fehlgeschlagene Verbindung oder keine Daten**

Die erste Verbindung kann sehr lange dauern (bis zu 15 Minuten oder länger).
Bei vorzeitig geschlossenen Verbindungen helfen ggf. Keep-Alive-Header.

---

## **Diagnosesketch**

Verwenden Sie das Diagnosebeispiel:

`File -> Examples -> TinyGSM -> tools -> Diagnostics`

Debugausgabe aktivieren:

`cpp #define TINYGSMDEBUG SerialMon
`

AT-Befehle ausgeben:

`cpp #define DUMPATCOMMANDS
`

```
#ifdef DUMPATCOMMANDS
  #include <StreamDebugger.h>
  StreamDebugger debugger(SerialAT, SerialMon);
  TinyGsm modem(debugger);
#else
  TinyGsm modem(SerialAT);
#endif
```

---

## **Probleme mit Web-Anfragen**

**TinyGSM** stellt nur TCP/SSL (OSI-Layer 4/5) bereit.
HTTP/MQTT liegen auf Layer 7.
Sie müssen daher Header korrekt selbst erzeugen oder Bibliotheken wie **HTTPClient** oder **PubSubClient** verwenden.

Tipps:
• Beispiel **WebClient** ansehen
• Alle erforderlichen Header setzen
• **`client.print()`** statt **`client.write("...")`** verwenden
• Jede Header-Zeile als zusammenhängende Zeichenkette senden
• Eine leere Zeile zwischen Headern und Body einfügen

---

## **SoftwareSerial-Probleme**

Bei **`SoftwareSerial`** funktionieren 115200 Baud oft nicht.
Versuchen Sie 57600, 38400 oder niedrigere Werte.
Korrekte TX/RX-Pins beachten.

---

## **ESP32-Hinweise**

• **HardwareSerial** kann zusätzliche Parameter für **`.begin()`** benötigen
• Für **HttpClient/HttpsClient** ggf. Core-Version aktualisieren

---

## **SIM800 und SSL**

Nur bestimmte Firmwareversionen unterstützen SSL.
Bei Problemen anderes Modul oder externe SSL-Bibliothek verwenden.

---

## **Welche SIM7000-Version verwenden?**

• **`TINYGSMMODEMSIM7000`** → kein SSL, bis zu 8 Verbindungen
• **`TINYGSMMODEMSIM7000SSL`** → SSL + ungesichert, bis zu 2 Verbindungen

Falls SSL nicht benötigt wird, beginnen Sie mit **`TINYGSMMODEMSIM7000`**.

=============================================================================

<img width="718" alt="gp1_0" src="https://github.com/user-attachments/assets/b34702ba-4825-4b5e-bfe8-b740d052a571" />


<img width="851" alt="gp1_1" src="https://github.com/user-attachments/assets/34b2a47e-84df-4f89-bc9e-64612cf5f96e" />


<img width="1046" alt="gp2" src="https://github.com/user-attachments/assets/41879c8a-a6e9-4cf5-a3c0-a9cabfbd598b" />


<img width="1161" alt="gp3" src="https://github.com/user-attachments/assets/3c224afc-cda7-4fca-88b8-b358146bc921" />


<img width="1245" alt="gp4" src="https://github.com/user-attachments/assets/1558b643-fb5a-4f5a-94fc-99e9fa1d5d5f" />

<img width="694" alt="gp5" src="https://github.com/user-attachments/assets/721bd17b-b35e-4dc9-b346-643a8f9d8084" />


<img width="1251" alt="gp6" src="https://github.com/user-attachments/assets/3f80c307-1281-43a1-90a8-ef1e89945e7b" />

<img width="1209" alt="gp7" src="https://github.com/user-attachments/assets/dc71342c-394f-4317-881c-56fc7db835bc" />

<img width="1195" alt="gp8" src="https://github.com/user-attachments/assets/f061335a-517b-472c-824f-1ca9d6ed5ebf" />


<img width="1128" alt="gp9" src="https://github.com/user-attachments/assets/96b1635f-7a89-43a9-b271-4a9de977d25b" />


<img width="1210" alt="gp10" src="https://github.com/user-attachments/assets/dfec02aa-4f42-41c2-9d61-0697d5db5f8d" />



<img width="1210" alt="gp10" src="https://github.com/user-attachments/assets/4b7660b4-805d-45bf-bbe0-c63086185649" />

<img width="761" alt="gp11" src="https://github.com/user-attachments/assets/22e7c95f-6fce-4571-9b41-e666494fa800" />


---

## Urheberrecht und Nutzungsbedingungen

### **© ALLE RECHTE VORBEHALTEN**

Dieses Projekt wurde von **Koffitse Aboudou** im Rahmen des Studiums an der **Technischen Hochschule Deggendorf (THD)** im Auftrag der **Mantro GmbH**  realisiert.

**Nutzungshinweise:**

* Jegliche Vervielfältigung, Verbreitung oder kommerzielle Nutzung des Inhalts, der Konzepte oder der Implementierungscodes – auch auszugsweise – ist ohne ausdrückliche schriftliche Genehmigung des Urhebers und der beteiligten Institutionen untersagt.
* Die Inhalte dienen ausschließlich Dokumentations- und Prüfungszwecken im akademischen Kontext. 

---
















