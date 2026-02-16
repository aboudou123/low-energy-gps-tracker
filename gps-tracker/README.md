

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

``markdown
Arduino Client-Hardware-Unterstützung

Diese Bibliothek lässt sich leicht mit vielen Skizzen integrieren, die Ethernet oder WiFi verwenden. PubSubClient (MQTT), Blynk, HTTP Client und Dateidownload-Beispiele sind enthalten.

TinyGSM ist klein
Das vollständige WebClient-Beispiel für Arduino Uno (über Software Serial) benötigt nur wenig Ressourcen:
`
Der Sketch verwendet 15022 Bytes (46%) des Programmspeichers. Maximal sind 32256 Bytes verfügbar.
Globale Variablen verwenden 574 Bytes (28%) des dynamischen Speichers, was 1474 Bytes für lokale Variablen lässt. Maximal sind 2048 Bytes verfügbar.
`
Die Arduino GSM-Bibliothek verwendet 15868 Bytes (49%) des Flash-Speichers und 1113 Bytes (54%) des RAM in einem ähnlichen Szenario. TinyGSM holt sich auch sanft Daten vom Modem (wann immer möglich), sodass es mit sehr wenig RAM arbeiten kann. Jetzt haben Sie mehr Platz für Ihre Experimente.

Unterstützte Modems
• SIMCom SIM800-Serie (SIM800A, SIM800C, SIM800L, SIM800H, SIM808, SIM868)
• SIMCom SIM900-Serie (SIM900A, SIM900D, SIM908, SIM968)
• SIMCom WCDMA/HSPA/HSPA+ Module (SIM5360, SIM5320, SIM5300E, SIM5300E/A)
• SIMCom LTE-Module (SIM7100E, SIM7500E, SIM7500A, SIM7600C, SIM7600E)
• SIMCom SIM7000E/A/G CAT-M1/NB-IoT Modul
• SIMCom SIM7070/SIM7080/SIM7090 CAT-M1/NB-IoT Modul
• SIMCom A7672X CAT-M1 Modul
• AI-Thinker A6, A6C, A7, A20
• ESP8266/ESP32 (AT-Befehlsoberfläche, ähnlich wie GSM-Modems)
• Digi XBee WiFi und Cellular (im XBee-Befehlsmodus)
• Neoway M590
• u-blox 2G, 3G, 4G und LTE Cat1 Cellular-Modems (viele Module, einschließlich LEON-G100, LISA-U2xx, SARA-G3xx, SARA-U2xx, TOBY-L2xx, LARA-R2xx, MPCI-L2xx)
• u-blox LTE-M/NB-IoT Modems (SARA-R4xx, SARA-N4xx, SARA-R5xx, aber NICHT SARA-N2xx)
• Sequans Monarch LTE Cat M1/NB1 (VZM20Q)
• Quectel BG96
• Quectel BG95
• Quectel M95
• Quectel MC60 (Alpha)

Unterstützte Boards/Module
• EnviroDIY LTE Bee, WiFi Bee
• Arduino MKR GSM 1400
• Sodaq GPRSbee, uBee
• Microduino GSM
• Adafruit FONA Mini Cellular GSM Breakout, 800/808 Shield, FONA 3G
• Industruino GSM
• Dragino NB-IoT Bee
• Digi XBee S6B, XBee LTE Cat 1, XBee3 LTE Cat 1, XBee3 CatM
• Nimbelink Skywire/Airgain NL-SW-LTE-QBG96, NL-SW-LTE-QBG95
• RAK WisLTE (Alpha)

Funktionen

Datenverbindungen
• TCP (HTTP, MQTT, Blynk, ...)
    - ALLE Module unterstützen TCP-Verbindungen
    - Die meisten Module unterstützen mehrere gleichzeitige Verbindungen:
        - A6/A7 - 8
        - ESP8266 - 5
        - Neoway M590 - 2
        - Quectel BG96 - 12
        - Quectel BG95 - 12
        - Quectel M95 - 6
        - Quectel MC60/MC60E - 6
        - Sequans Monarch - 6
        - SIM 800/900 - 5
        - SIM 5360/5320/5300/7100 - 10
        - SIM7000 - 8 möglich ohne SSL, nur 2 mit SSL
        - SIM 7070/7080/7090 - 12
        - SIM 7500/7600/7800 - 10
        - SIM A7672X - 10
        - u-blox 2G/3G - 7
        - u-blox SARA R4/N4 - 7
        - Digi XBee - nur 1 Verbindung unterstützt!
• UDP
    - Noch nicht auf einem Modul unterstützt, könnte aber eines Tages kommen
• SSL/TLS (HTTPS)
    - Unterstützt auf:
        - SIM800, SIM7000, A7672X, u-Blox, XBee mobil, ESP8266, Sequans Monarch und Quectel BG95 und BG96
        - Hinweis: nur einige Geräte-Modelle oder Firmware-Versionen verfügen über diese Funktion (SIM8xx R14.18, A7 usw.)
    - Noch nicht unterstützt auf:
        - SIM 5360/5320/7100, SIM 7500/7600/7800
    - Nicht möglich auf:
        - SIM900, A6/A7, Neoway M590, XBee WiFi
    - Wie TCP unterstützen die meisten Module gleichzeitige Verbindungen
    - TCP- und SSL-Verbindungen können in der Regel gemischt werden, bis zur maximal möglichen Anzahl an Verbindungen

USSD
• Senden von USSD-Anfragen und Decodierung von 7, 8, 16-Bit-Antworten
    - Unterstützt auf:
        - Alle SIMCom-Modems, Quectel-Modems, die meisten u-blox
    - Nicht möglich auf:
        - XBee, u-blox SARA R4/N4, ESP8266 (offensichtlich)

SMS
• Nur das Senden von SMS wird unterstützt, nicht das Empfangen
    - Unterstützt auf allen Mobilfunkmodulen

Sprachanrufe
• Unterstützt auf:
    - SIM800/SIM900, SIM7600, A6/A7, Quectel-Modems, u-blox
• Noch nicht unterstützt auf:
    - SIM7000, SIM5360/5320/7100, SIM7500/7800, VZM20Q (Monarch)
• Nicht möglich auf:
    - XBee (jeder Typ), u-blox SARA R4/R5/N4, Neoway M590, ESP8266 (offensichtlich)
• Funktionen:
    - Wählen, auflegen
    - DTMF senden

Standort
• GPS/GNSS
    - SIM808, SIM7000, SIM7500/7600/7800, BG96, BG95, u-blox
    - HINWEIS: u-blox-Chips haben KEIN eingebautes GPS - diese Funktionalität funktioniert nur, wenn ein sekundäres GPS mit dem primären Mobilfunkchip über I2C verbunden ist
• GSM-Standortdienst
    - SIM800, SIM7000, Quectel, u-blox

Erste Schritte
Erste Schritte
Verwenden Sie Ihr Telefon:
    - Deaktivieren Sie den PIN-Code auf der SIM-Karte
    - Überprüfen Sie Ihr Guthaben
    - Überprüfen Sie, ob APN, Benutzer, Passwort korrekt sind und Sie Internet haben
Stellen Sie sicher, dass die SIM-Karte korrekt in das Modul eingelegt ist
Stellen Sie sicher, dass die GSM-Antenne fest angeschlossen ist
Stellen Sie sicher, dass Sie eine stabile Stromversorgung für das Modul von mindestens 2A haben.
Überprüfen Sie, ob die serielle Verbindung funktioniert (Hardware Serial wird empfohlen)
   Senden Sie einen `AT`-Befehl mit diesem Sketch
Probieren Sie das WebClient Beispiel aus

Schreiben Sie Ihren eigenen Code

Der allgemeine Ablauf Ihres Codes sollte folgendermaßen aussehen:
• Definieren Sie das Modul, das Sie verwenden (wählen Sie eines und nur eines)
    - z. B. `#define TINYGSMMODEMSIM800`
• Fügen Sie TinyGSM hinzu
    - `#include <TinyGsmClient.h>`
• Erstellen Sie eine TinyGSM-Modeminstanz
    - `TinyGsm modem(SerialAT);`
• Erstellen Sie eine oder mehrere TinyGSM-Clientinstanzen
    - Für eine einzelne Verbindung verwenden Sie
        - `TinyGsmClient client(modem);`
        oder
        `TinyGsmClientSecure client(modem);` (auf unterstützten Modulen)
    - Für mehrere Verbindungen (auf unterstützten Modulen) verwenden Sie:
        - `TinyGsmClient clientX(modem, 0);`, `TinyGsmClient clientY(modem, 1);`, usw.
          oder
        - `TinyGsmClientSecure clientX(modem, 0);`, `TinyGsmClientSecure clientY(modem, 1);`, usw.
    - Sichere und unsichere Clients können in der Regel gemischt verwendet werden, wenn mehrere Verbindungen verwendet werden.
    - Die Gesamtanzahl der möglichen Verbindungen variiert je nach Modul
• Beginnen Sie Ihre serielle Kommunikation und setzen Sie alle Ihre Pins gemäß den Anforderungen zum Betrieb Ihres Moduls in Betrieb.
    - Die Beispiele versuchen, die Baudrate des Moduls zu erraten. In funktionsfähigem Code sollten Sie eine festgelegte Baudrate verwenden.
• Warten Sie, bis das Modul bereit ist (das kann bis zu 6 Sekunden dauern, je nach Modul)
• Initialisieren Sie das Modem
    - `modem.init()` oder `modem.restart()`
    - Ein Neustart dauert in der Regel länger als eine Initialisierung, stellt jedoch sicher, dass das Modul keine bestehenden Verbindungen hat
• Entsperren Sie Ihre SIM, falls erforderlich:
    - `modem.simUnlock(GSMPIN)`
• Wenn Sie WiFi verwenden, geben Sie Ihre SSID-Informationen an:
    - `modem.networkConnect(wifiSSID, wifiPass)`
    - Die Netzwerkanmeldung sollte bei Mobilfunkmodulen automatisch erfolgen
• Warten Sie, bis die Netzwerkanmeldung erfolgreich war
    - `modem.waitForNetwork(600000L)`
• Wenn Sie Mobilfunk verwenden, stellen Sie die GPRS- oder EPS-Datenverbindung nach der erfolgreichen Anmeldung im Netzwerk her
    - `modem.gprsConnect(apn, gprsUser, gprsPass)` (oder einfach `modem.gprsConnect(apn)`)
    - Der gleiche Befehl wird sowohl für GPRS- als auch für EPS-Verbindungen verwendet
    - Wenn Sie eine Digi-Marken-Mobilfunk-XBee verwenden, müssen Sie Ihre GPRS/EPS-Verbindungsinformationen vor der Wartezeit für das Netzwerk festlegen. Dies gilt NUR für Digi-Mobilfunk-XBees! Für alle anderen Mobilfunkmodule verwenden Sie die GPRS-Verbindungsfunktion nach der Netzwerkanmeldung.
• Verbinden Sie den TCP- oder SSL-Client
    `client.connect(server, port)`
• Senden Sie Ihre Daten aus.

Wie funktioniert es?

Viele GSM-Modems, WiFi- und Funkmodule können gesteuert werden, indem AT-Befehle über Serial gesendet werden. TinyGSM weiß, welche Befehle gesendet werden müssen und wie AT-Antworten behandelt werden, und verpackt dies in die standardisierte Arduino-Client-Oberfläche.

Diese Bibliothek ist in allen ihrer Kommunikation "blockierend". Abhängig von der Funktion kann Ihr Code für längere Zeit blockiert werden, während auf die Antworten des Moduls gewartet wird. Abgesehen von den offensichtlichen (d.h. waitForNetwork()) können auch mehrere andere Funktionen Ihren Code für bis zu mehrere Minuten blockieren. Die Funktionen gprsConnect() und client.connect() blockieren normalerweise am längsten, besonders in Gebieten mit schlechterem Empfang. Das Herunterfahren und Neustarten des Moduls kann ebenfalls recht langsam sein.

Diese Bibliothek unterstützt keine Art von "Hardware"- oder Pin-steuerungsfunktionen für die Module. Wenn Sie Ihr Modul ein- oder zurücksetzen müssen, indem Sie eine Art von Hoch/Niedrig/Hoch-Pin-Sequenz verwenden, müssen Sie diese Funktionen selbst schreiben.

API-Referenz

Für GPRS-Datenströme bietet diese Bibliothek die standardisierte Arduino Client-Schnittstelle. Für zusätzliche Funktionen siehe dieses Beispiel-Sketch

Problembehandlung
Sicherstellen stabiler Daten- und Stromverbindungen

Die meisten Module benötigen bis zu 2A, um ordnungsgemäß eine Verbindung zum Netzwerk herzustellen. Das ist 4x, was ein "Standard"-USB liefern kann! Die Verbesserung der Stromversorgung löst tatsächlich Stabilitätsprobleme in vielen Fällen!
• Lesen Sie über Stromversorgung Ihres Moduls.
• Halten Sie Ihre Drähte so kurz wie möglich
• Erwägen Sie, sie für eine stabile Verbindung zu löten
• Platzieren Sie Ihre Drähte nicht neben Störsignalquellen (Buck-Convertern, Antennen, Oszillatoren usw.)
• Wenn alles andere zu funktionieren scheint, Sie aber nicht in der Lage sind, eine Verbindung zum Netzwerk herzustellen, überprüfen Sie Ihre Stromversorgung!

Baudraten

Die meisten Module unterstützen eine Art von "Auto-Baud"-Funktion, bei der das Modul versucht, seine Baudrate an das, was es empfängt, anzupassen. TinyGSM implementiert auch seine eigene Auto-Baud-Funktion (TinyGsmAutoBaud(SerialAT, GSMAUTOBAUDMIN, GSMAUTOBAUDMAX);). Obwohl dies beim ersten Verbinden mit einem Modul und beim Testen sehr nützlich ist, sollten diese in jedem Produktionscode NICHT verwendet werden. Sobald Sie die Kommunikation mit dem Modul hergestellt haben, stellen Sie die Baudrate mit der Funktion setBaud(#) ein und bleiben Sie bei dieser Rate.

Defekte Anfangs-Konfiguration

Manchmal (insbesondere wenn Sie mit AT-Befehlen experimentiert haben), kann Ihre Modulkonfiguration ungültig werden. Dies kann zu Problemen führen, wie zum Beispiel:

  Keine Verbindung zum GPRS-Netzwerk
  Keine Verbindung zum Server
  Gesendete/erhaltene Daten enthalten ungültige Bytes
  usw.

Um das Modul auf Werkseinstellungen zurückzusetzen, verwenden Sie dieses Sketch:
  Datei -> Beispiele -> TinyGSM -> Werkzeuge -> FactoryReset

In einigen Fällen müssen Sie möglicherweise einen anfänglichen APN festlegen, um eine Verbindung zum Mobilfunknetz herzustellen. Versuchen Sie, die Funktion `gprsConnect(APN)` zu verwenden, um einen anfänglichen APN festzulegen, wenn Sie sich nicht im Netzwerk registrieren können. Möglicherweise müssen Sie den APN nach der Registrierung erneut festlegen. (In den meisten Fällen sollten Sie den APN nach der Registrierung festlegen.)

Fehlgeschlagene Verbindung oder keine Daten empfangen

Die erste Verbindung mit einer neuen SIM-Karte, einem neuen Modul oder an einem neuen Standort/Turm kann SEHR lange dauern - bis zu 15 Minuten oder sogar mehr, insbesondere wenn die Signalqualität nicht hervorragend ist. Wenn es sich um Ihre erste Verbindung handelt, müssen Sie möglicherweise Ihre Wartezeiten anpassen und möglicherweise zum Mittagessen gehen, während Sie warten.

Wenn Sie in der Lage sind, eine TCP-Verbindung herzustellen, die Verbindung jedoch schließen, bevor Sie Daten empfangen, versuchen Sie, einen Keep-Alive-Header zu Ihrer Anfrage hinzuzufügen. Einige Module (z. B. das SIM7000 im SSL-Modus) werfen sofort alle ungelesenen Daten weg, wenn der Remoteserver die Verbindung schließt - manchmal ohne jegliche Benachrichtigung, dass Daten zunächst eingetroffen sind. Beim Einsatz von MQTT müssen Sie möglicherweise Ihr Keep-Alive-Intervall (PINGREQ/PINGRESP) reduzieren, um eine kontinuierliche Verbindung aufrechtzuerhalten.

Diagnose-Sketch

Verwenden Sie dieses Sketch, um SIM-Karten- und GPRS-Verbindungsprobleme zu diagnostizieren:
  Datei -> Beispiele -> TinyGSM -> Werkzeuge -> Diagnostics

Wenn die Diagnose fehlschlägt, kommentieren Sie diese Zeile aus, um einige Debugging-Kommentare aus der Bibliothek zu erhalten:
`cpp
#define TINYGSMDEBUG SerialMon
`
In jedem benutzerdefinierten Code muss `TINYGSMDEBUG` definiert werden, bevor die TinyGSM-Bibliothek eingeschlossen wird.

Wenn Sie keine offensichtlichen Fehler in der Bibliotheks-Diagnose sehen können, verwenden Sie StreamDebugger, um die gesamte AT-Befehlssequenz an den Haupt-Seriellen Port zu kopieren. Im Diagnosebeispiel kommentieren Sie einfach die Zeile aus:
`cpp
#define DUMPATCOMMANDS
`
In benutzerdefiniertem Code können Sie dieses Snippet hinzufügen:
`cpp
#ifdef DUMPATCOMMANDS
  #include <StreamDebugger.h>
  StreamDebugger debugger(SerialAT, SerialMon);
  TinyGsm modem(debugger);
#else
  TinyGsm modem(SerialAT);
#endif
`

Probleme mit der Webanfrage-Formatierung - "aber es funktioniert mit PostMan"

Diese Bibliothek öffnet eine TCP- (oder SSL-) Verbindung zu einem Server. In der OSI-Modell ist das Schicht 4 (oder 5 für SSL). HTTP (GET/POST), MQTT und die meisten anderen Funktionen, die Sie vermutlich verwenden möchten, leben in der Regel auf Schicht 7. Das bedeutet, dass Sie entweder die oberste Schicht manuell codieren oder eine andere Bibliothek (wie HTTPClient oder PubSubClient) verwenden müssen, um dies für Sie zu tun. Werkzeuge wie PostMan zeigen auch Schicht 7, nicht Schicht 4/5 wie TinyGSM. Wenn Sie erfolgreich eine Verbindung zu einem Server herstellen, aber Antworten wie "schlechte Anfrage" (oder keine Antwort) erhalten, liegt das Problem wahrscheinlich an Ihrer Formatierung. Hier sind einige Tipps zum manuellen Schreiben von Schicht 7 (insbesondere HTTP-Anfragen):
• Sehen Sie sich das "WebClient"-Beispiel an
• Stellen Sie sicher, dass Sie alle erforderlichen Header einschließen.
    - Wenn Sie mit PostMan testen, stellen Sie sicher, dass Sie die "automatisch generierten" Header einsehen; Sie werden wahrscheinlich überrascht sein, wie viele von ihnen es gibt.
• Verwenden Sie `client.print("...")`, oder `client.write(buf, #)`, oder sogar `client.write(String("..."))`, nicht `client.write("...")`, um zu verhindern, dass Text zeilenweise (im Schreibmaschinenstil) ausgegeben wird.
• Schließen Sie den gesamten Inhalt jedes Headers oder jeder Zeile innerhalb einer einzigen Zeichenfolge oder Druckanweisung ein
    - verwenden Sie
    `cpp
    client.print(String("GET ") + resource + " HTTP/1.1\r\n");
    `
    anstelle von
    `cpp
    client.print("GET ");
    client.print(resource);
    client.println(" HTTP/1.1")
    `
• Stellen Sie sicher, dass zwischen dem letzten Header und dem Inhalt einer POST-Anfrage eine vollständig leere Zeile steht.
    - Fügen Sie zwei Zeilen zum letzten Header hinzu `client.print("....\r\n\r\n")` oder verwenden Sie ein zusätzliches `client.println()`
    - Dies ist eine HTTP-Anforderung und leicht zu übersehen.

SoftwareSerial-Probleme

Bei der Verwendung von `SoftwareSerial` (auf Uno, Nano usw.) könnte die Geschwindigkeit 115200 nicht funktionieren. Versuchen Sie, 57600, 38400 oder sogar niedriger auszuwählen - diejenige, die am besten für Sie funktioniert. In einigen Fällen ist 9600 instabil, aber die Verwendung von 38400 hilft usw. Stellen Sie sicher, dass Sie die richtigen TX/RX-Pins im Sketch festgelegt haben. Bitte beachten Sie, dass nicht jeder Arduino-Pin als TX- oder RX-Pin dienen kann. Lesen Sie hier mehr über SoftSerial-Optionen und -Konfiguration hier und hier.

ESP32 Hinweise
HardwareSerial

Bei der Verwendung von ESP32 HardwareSerial müssen Sie möglicherweise zusätzliche Parameter beim .begin()-Aufruf angeben.

HttpClient
Sie können die Beispiele von HttpClient oder HttpsClient nicht mit ESP32 Core 1.0.2 kompilieren. Aktualisieren Sie auf 1.0.3, downgraden Sie auf Version 1.0.1 oder verwenden Sie das WebClient-Beispiel.

SAMD21

Bei der Verwendung von SAMD21-basierten Boards müssen Sie möglicherweise einen Sercom-UART-Port anstelle von Serial1 verwenden.

SIM800 und SSL

Einige, aber nicht alle, Versionen des SIM800 unterstützen SSL. Die Unterstützung von SSL hängt von der Firmware-Version und dem individuellen Modul ab. Die Benutzer haben unterschiedliche Erfahrungswerte in Bezug auf die Verwendung von SSL auf dem SIM800, selbst bei anscheinend identischer Firmware. Wenn Sie SSL benötigen und es auf Ihrem SIM800 anscheinend nicht funktioniert, versuchen Sie ein anderes Modul oder verwenden Sie eine sekundäre SSL-Bibliothek.

Welche Version des SIM7000-Codes zu verwenden

Es gibt zwei Versionen des SIM7000-Codes, eine mit TINYGSMMODEMSIM7000 und eine andere mit TINYGSMMODEMSIM7000SSL. Die Version TINYGSMMODEMSIM7000 unterstützt kein SSL, unterstützt jedoch bis zu 8 gleichzeitige Verbindungen. Die Version TINYGSMMODEMSIM7000SSL unterstützt sowohl SSL als auch ungesicherte Verbindungen mit bis zu 2 gleichzeitigen Verbindungen. Warum gibt es also zwei Versionen?

Die "SSL"-Version verwendet die "Anwendungs"-Befehle des SIM7000, während die andere die "TCP-IP-Werkzeugkiste" verwendet. Abhängig von Ihrer Region/Firmware funktioniert möglicherweise die eine oder die andere nicht für Sie. Versuchen Sie beide und verwenden Sie die stabilere.

Wenn Sie kein SSL benötigen, empfehle ich, mit TINYGSMMODEMSIM7000 zu beginnen.
``



# Arduino Client interface support

This library is easy to integrate with lots of sketches which use Ethernet or WiFi.
**PubSubClient ([MQTT](http://mqtt.org/))**, **[Blynk](http://blynk.cc)**, **HTTP Client** and **File Download** examples are provided.



### TinyGSM is tiny
The complete WebClient example for Arduino Uno (via Software Serial) takes little resources:
```
Sketch uses 15022 bytes (46%) of program storage space. Maximum is 32256 bytes.
Global variables use 574 bytes (28%) of dynamic memory, leaving 1474 bytes for local variables. Maximum is 2048 bytes.
```
Arduino GSM library uses 15868 bytes (49%) of Flash and 1113 bytes (54%) of RAM in a similar scenario.
TinyGSM also pulls data gently from the modem (whenever possible), so it can operate on very little RAM.
**Now, you have more space for your experiments.**


## Supported modems

- SIMCom SIM800 series (SIM800A, SIM800C, SIM800L, SIM800H, SIM808, SIM868)
- SIMCom SIM900 series (SIM900A, SIM900D, SIM908, SIM968)
- SIMCom WCDMA/HSPA/HSPA+ Modules (SIM5360, SIM5320, SIM5300E, SIM5300E/A)
- SIMCom LTE Modules (SIM7100E, SIM7500E, SIM7500A, SIM7600C, SIM7600E)
- SIMCom SIM7000E/A/G CAT-M1/NB-IoT Module
- SIMCom SIM7070/SIM7080/SIM7090 CAT-M1/NB-IoT Module
- SIMCom A7672X CAT-M1 Module
- AI-Thinker A6, A6C, A7, A20
- ESP8266/ESP32 (AT commands interface, similar to GSM modems)
- Digi XBee WiFi and Cellular (using XBee command mode)
- Neoway M590
- u-blox 2G, 3G, 4G, and LTE Cat1 Cellular Modems (many modules including LEON-G100, LISA-U2xx, SARA-G3xx, SARA-U2xx, TOBY-L2xx, LARA-R2xx, MPCI-L2xx)
- u-blox LTE-M/NB-IoT Modems (SARA-R4xx, SARA-N4xx, SARA-R5xx, _but NOT SARA-N2xx_)
- Sequans Monarch LTE Cat M1/NB1 (VZM20Q)
- Quectel BG96
- Quectel BG95
- Quectel M95
- Quectel MC60 ***(alpha)***

### Supported boards/modules
- EnviroDIY LTE Bee, WiFi Bee
- Arduino MKR GSM 1400
- Sodaq GPRSbee, uBee
- Microduino GSM
- Adafruit FONA Mini Cellular GSM Breakout, 800/808 Shield, FONA 3G
- Industruino GSM
- Dragino NB-IoT Bee
- Digi XBee S6B, XBee LTE Cat 1, XBee3 LTE Cat 1, XBee3 CatM
- Nimbelink Skywire/Airgain NL-SW-LTE-QBG96, NL-SW-LTE-QBG95
- RAK WisLTE ***(alpha)***

## Features

**Data connections**
- TCP (HTTP, MQTT, Blynk, ...)
    - ALL modules support TCP connections
    - Most modules support multiple simultaneous connections:
        - A6/A7 - 8
        - ESP8266 - 5
        - Neoway M590 - 2
        - Quectel BG96 - 12
        - Quectel BG95 - 12
        - Quectel M95 - 6
        - Quectel MC60/MC60E - 6
        - Sequans Monarch - 6
        - SIM 800/900 - 5
        - SIM 5360/5320/5300/7100 - 10
        - SIM7000 - 8 possible without SSL, only 2 with
        - SIM 7070/7080/7090 - 12
        - SIM 7500/7600/7800 - 10
        - SIM A7672X - 10
        - u-blox 2G/3G - 7
        - u-blox SARA R4/N4 - 7
        - Digi XBee - _only 1 connection supported!_
- UDP
    - Not yet supported on any module, though it may be some day
- SSL/TLS (HTTPS)
    - Supported on:
        - SIM800, SIM7000, A7672X, u-Blox, XBee _cellular_, ESP8266, Sequans Monarch and Quectel BG95 and BG96
        - Note:  **only some device models or firmware revisions have this feature** (SIM8xx R14.18, A7, etc.)
    - Not yet supported on:
        - SIM 5360/5320/7100, SIM 7500/7600/7800
    - Not possible on:
        - SIM900, A6/A7, Neoway M590, XBee _WiFi_
    - Like TCP, most modules support simultaneous connections
    - TCP and SSL connections can usually be mixed up to the total number of possible connections

**USSD**
- Sending USSD requests and decoding 7,8,16-bit responses
    - Supported on:
        - All SIMCom modems, Quectel modems, most u-blox
    - Not possible on:
        - XBee, u-blox SARA R4/N4, ESP8266 (obviously)

**SMS**
- Only _sending_ SMS is supported, not receiving
    - Supported on all cellular modules

**Voice Calls**
- Supported on:
    - SIM800/SIM900, SIM7600, A6/A7, Quectel modems, u-blox
- Not yet supported on:
    - SIM7000, SIM5360/5320/7100, SIM7500/7800, VZM20Q (Monarch)
- Not possible on:
    -  XBee (any type), u-blox SARA R4/R5/N4, Neoway M590, ESP8266 (obviously)
- Functions:
    - Dial, hangup
    - DTMF sending

**Location**
- GPS/GNSS
    - SIM808, SIM7000, SIM7500/7600/7800, BG96, BG95, u-blox
    - NOTE:  u-blox chips do _NOT_ have embedded GPS - this functionality only works if a secondary GPS is connected to primary cellular chip over I2C
- GSM location service
    - SIM800, SIM7000, Quectel, u-blox

## Getting Started

#### First Steps

  1. Using your phone:
    - Disable PIN code on the SIM card
    - Check your balance
    - Check that APN, User, Pass are correct and you have internet
  2. Ensure the SIM card is correctly inserted into the module
  3. Ensure that GSM antenna is firmly attached
  4. Ensure that you have a stable power supply to the module of at least **2A**.
  5. Check if serial connection is working (Hardware Serial is recommended)
     Send an ```AT``` command using [this sketch](tools/AT_Debug/AT_Debug.ino)
  6. Try out the [WebClient](https://github.com/vshymanskyy/TinyGSM/blob/master/examples/WebClient/WebClient.ino) example

#### Writing your own code

The general flow of your code should be:
- Define the module that you are using (choose one and only one)
    - ie, ```#define TINY_GSM_MODEM_SIM800```
- Included TinyGSM
    - ```#include <TinyGsmClient.h>```
- Create a TinyGSM modem instance
    - ```TinyGsm modem(SerialAT);```
- Create one or more TinyGSM client instances
    - For a single connection, use
        - ```TinyGsmClient client(modem);```
        or
        ```TinyGsmClientSecure client(modem);``` (on supported modules)
    - For multiple connections (on supported modules) use:
        - ```TinyGsmClient clientX(modem, 0);```, ```TinyGsmClient clientY(modem, 1);```, etc
          or
        - ```TinyGsmClientSecure clientX(modem, 0);```, ```TinyGsmClientSecure clientY(modem, 1);```, etc
    - Secure and insecure clients can usually be mixed when using multiple connections.
    - The total number of connections possible varies by module
- Begin your serial communication and set all your pins as required to power your module and bring it to full functionality.
    - The examples attempt to guess the module's baud rate.  In working code, you should use a set baud.
- Wait for the module to be ready (could be as much as 6s, depending on the module)
- Initialize the modem
    - ```modem.init()``` or ```modem.restart()```
    - restart generally takes longer than init but ensures the module doesn't have lingering connections
- Unlock your SIM, if necessary:
    - ```modem.simUnlock(GSM_PIN)```
- If using **WiFi**, specify your SSID information:
    - ```modem.networkConnect(wifiSSID, wifiPass)```
    - Network registration should be automatic on cellular modules
- Wait for network registration to be successful
    - ```modem.waitForNetwork(600000L)```
- If using cellular, establish the GPRS or EPS data connection _after_ your are successfully registered on the network
    - ```modem.gprsConnect(apn, gprsUser, gprsPass)``` (or simply ```modem.gprsConnect(apn)```)
    - The same command is used for both GPRS or EPS connection
    - If using a **Digi** brand cellular XBee, you must specify your GPRS/EPS connection information _before_ waiting for the network.  This is true ONLY for _Digi cellular XBees_!  _For all other cellular modules, use the GPRS connect function after network registration._
- Connect the TCP or SSL client
    ```client.connect(server, port)```
- Send out your data.


## How does it work?

Many GSM modems, WiFi and radio modules can be controlled by sending AT commands over Serial.
TinyGSM knows which commands to send, and how to handle AT responses, and wraps that into standard Arduino Client interface.

This library is "blocking" in all of its communication.
Depending on the function, your code may be blocked for a long time waiting for the module responses.
Apart from the obvious (ie, `waitForNetwork()`) several other functions may block your code for up to several *minutes*.
The `gprsConnect()` and `client.connect()` functions commonly block the longest, especially in poorer service regions.
The module shutdown and restart may also be quite slow.

This libary *does not* support any sort of "hardware" or pin level controls for the modules.
If you need to turn your module on or reset it using some sort of High/Low/High pin sequence, you must write those functions yourself.

## API Reference

For GPRS data streams, this library provides the standard [Arduino Client](https://www.arduino.cc/en/Reference/ClientConstructor) interface.
For additional functions, please refer to [this example sketch](examples/AllFunctions/AllFunctions.ino)

## Troubleshooting

### Ensure stable data & power connection

Most modules require _**as much as 2A**_ to properly connect to the network.
This is 4x what a "standard" USB will supply!
Improving the power supply actually solves stability problems in **many** cases!
- Read about [**powering your module**](https://github.com/vshymanskyy/TinyGSM/wiki/Powering-GSM-module).
- Keep your wires as short as possible
- Consider soldering them for a stable connection
- Do not put your wires next to noisy signal sources (buck converters, antennas, oscillators etc.)
- If everything else seems to be working but you are unable to connect to the network, check your power supply!

### Baud rates

Most modules support some sort of "auto-bauding" feature where the module will attempt to adjust it's baud rate to match what it is receiving.
TinyGSM also implements its own auto bauding function (`TinyGsmAutoBaud(SerialAT, GSM_AUTOBAUD_MIN, GSM_AUTOBAUD_MAX);`).
While very useful when initially connecting to a module and doing tests, these should **NOT** be used in any sort of production code.
Once you've established communication with the module, set the baud rate using the `setBaud(#)` function and stick with that rate.

### Broken initial configuration

Sometimes (especially if you played with AT commands), your module configuration may become invalid.
This may result in problems such as:

 * Can't connect to the GPRS network
 * Can't connect to the server
 * Sent/received data contains invalid bytes
 * etc.

To return module to **Factory Defaults**, use this sketch:
  File -> Examples -> TinyGSM -> tools -> [FactoryReset](https://github.com/vshymanskyy/TinyGSM/blob/master/tools/FactoryReset/FactoryReset.ino)

In some cases, you may need to set an initial APN to connect to the cellular network.
Try using the ```gprsConnect(APN)``` function to set an initial APN if you are unable to register on the network.
You may need set the APN again after registering.
(In most cases, you should set the APN after registration.)

### Failed connection or no data received

The first connection with a new SIM card, a new module, or at a new location/tower may take a *LONG* time - up to 15 minutes or even more, especially if the signal quality isn't excellent.
If it is your first connection, you may need to adjust your wait times and possibly go to lunch while you're waiting.

If you are able to open a TCP connection but have the connection close before receiving data, try adding a keep-alive header to your request.
Some modules (ie, the SIM7000 in SSL mode) will immediately throw away any un-read data when the remote server closes the connection - sometimes without even giving a notification that data arrived in the first place.
When using MQTT, to keep a continuous connection you may need to reduce your keep-alive interval (PINGREQ/PINGRESP).

### Diagnostics sketch

Use this sketch to help diagnose SIM card and GPRS connection issues:
  File -> Examples -> TinyGSM -> tools -> [Diagnostics](https://github.com/vshymanskyy/TinyGSM/blob/master/tools/Diagnostics/Diagnostics.ino)

If the diagnostics fail, uncomment this line to output some debugging comments from the library:
```cpp
#define TINY_GSM_DEBUG SerialMon
```
In any custom code, ```TINY_GSM_DEBUG``` must be defined before including the TinyGSM library.

If you are unable to see any obvious errors in the library debugging, use [StreamDebugger](https://github.com/vshymanskyy/StreamDebugger) to copy the entire AT command sequence to the main serial port.
In the diagnostics example, simply uncomment the line:
```cpp
#define DUMP_AT_COMMANDS
```
In custom code, you can add this snippit:
```cpp
#ifdef DUMP_AT_COMMANDS
  #include <StreamDebugger.h>
  StreamDebugger debugger(SerialAT, SerialMon);
  TinyGsm modem(debugger);
#else
  TinyGsm modem(SerialAT);
#endif
```

### Web request formatting problems - "but it works with PostMan"

This library opens a TCP (or SSL) connection to a server.
In the [OSI model](https://en.wikipedia.org/wiki/OSI_model), that's [layer 4](http://www.tcpipguide.com/free/t_TransportLayerLayer4.htm) (or 5 for SSL).
HTTP (GET/POST), MQTT, and most of the other functions you probably want to use live up at [layer 7](http://www.tcpipguide.com/free/t_ApplicationLayerLayer7.htm).
This means that you need to either manually code the top layer or use another library (like [HTTPClient](https://github.com/arduino-libraries/ArduinoHttpClient) or [PubSubClient](https://pubsubclient.knolleary.net/)) to do it for you.
Tools like [PostMan](https://www.postman.com/) also show layer 7, not layer 4/5 like TinyGSM.
If you are successfully connecting to a server, but getting responses of "bad request" (or no response), the issue is probably your formatting.
Here are some tips for writing layer 7 (particularly HTTP request) manually:
- Look at the "WebClient" example
- Make sure you are including all required headers.
    - If you are testing with PostMan, make sure you un-hide and look at the "auto-generated" headers; you'll probably be surprised by how many of them there are.
- Use ```client.print("...")```, or ```client.write(buf, #)```, or even ```client.write(String("..."))```, not ```client.write("...")``` to help prevent text being sent out one character at a time (typewriter style)
- Enclose the entirety of each header or line within a single string or print statement
    - use
    ```cpp
    client.print(String("GET ") + resource + " HTTP/1.1\r\n");
    ```
    instead of
    ```cpp
    client.print("GET ");
    client.print(resource);
    client.println(" HTTP/1.1")
    ```
- Make sure there is one entirely blank line between the last header and the content of any POST request.
    - Add two lines to the last header ```client.print("....\r\n\r\n")``` or put in an extra ```client.println()```
    - This is an HTTP requirement and is really easy to miss.

### SoftwareSerial problems

When using ```SoftwareSerial``` (on Uno, Nano, etc), the speed **115200** may not work.
Try selecting **57600**, **38400**, or even lower - the one that works best for you.
In some cases **9600** is unstable, but using **38400** helps, etc.
Be sure to set correct TX/RX pins in the sketch. Please note that not every Arduino pin can serve as TX or RX pin.
**Read more about SoftSerial options and configuration [here](https://www.pjrc.com/teensy/td_libs_AltSoftSerial.html) and [here](https://www.arduino.cc/en/Reference/SoftwareSerial).**

### ESP32 Notes

#### HardwareSerial

When using ESP32 `HardwareSerial`, you may need to specify additional parameters to the `.begin()` call.


#### HttpClient
You will not be able to compile the HttpClient or HttpsClient examples with ESP32 core 1.0.2.  Upgrade to 1.0.3, downgrade to version 1.0.1 or use the WebClient example.

### SAMD21

When using SAMD21-based boards, you may need to use a sercom uart port instead of `Serial1`.


### SIM800 and SSL

Some, but not all, versions of the SIM800 support SSL.
Having SSL support depends on the firmware version and the individual module.
Users have had varying levels of success in using SSL on the SIM800 even with apparently identical firmware.
If you need SSL and it does not appear to be working on your SIM800, try a different module or try using a secondary SSL library.

### Which version of the SIM7000 code to use

There are two versions of the SIM7000 code, one using `TINY_GSM_MODEM_SIM7000` and another with `TINY_GSM_MODEM_SIM7000SSL`.
The `TINY_GSM_MODEM_SIM7000` version *does not support SSL* but supports up to 8 simultaneous connections.
The `TINY_GSM_MODEM_SIM7000SSL` version supports both SSL *and unsecured connections* with up to 2 simultaneous connections.
So why are there two versions?

The "SSL" version uses the SIM7000's "application" commands while the other uses the "TCP-IP toolkit".
Depending on your region/firmware, one or the other may not work for you.
Try both and use whichever is more stable.

If you do not need SSL, I recommend starting with `TINY_GSM_MODEM_SIM7000`.
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
















