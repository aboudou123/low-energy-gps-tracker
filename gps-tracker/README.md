

### Arduino Client interface support
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

### Goouuu Tech IOT-GA6 vs AI-Thinker A6 confusion

It turns out that **Goouuu Tech IOT-GA6** is not the same as **AI-Thinker A6**. Unfortunately IOT-GA6 is not supported out of the box yet. There are some hints that IOT-GA6 firmware may be updated to match A6... See [this topic](https://github.com/vshymanskyy/TinyGSM/issues/164).

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
<img width="761" alt="gp11" src="https://github.com/user-attachments/assets/8f34de26-a23b-4441-a9cc-b53ae09a5f2f" />













