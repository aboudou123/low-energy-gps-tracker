# low-energy-gps-tracker

``markdown

Low-Energy GPS Tracker
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

Research Objective
• Explain what GPS and other tracking technologies are.
• Describe the structure and functionality of the GPS system.
• Research the technologies involved in developing GPS tracking systems.
• Compare various IoT technologies: Low-Power Wide-Area Network (LPWA).

What is GPS?
Global Positioning System (GPS) is a network of satellites that orbit the Earth, providing positional information about their locations.

Segments of GPS
Space Segment: The satellites themselves.
Ground Segment: The infrastructure that controls the satellites.
User Segment: The devices that receive GPS signals.

Primary Functions
• Positioning and coordinates.
• Measuring distance and direction between waypoints.
• Progress reporting for travel.
• Accurate timekeeping.

Literature Review
• IBM Tracking Solution: Investigates advanced tracking methodologies and their applications.

Problem Statement
Poaching threatens thousands of endangered species annually. Research indicates that animal movement varies based on perceived threats. The aim is to develop an early warning system that alerts rangers to poachers' presence using a long-range IoT tracking system with LoRaWAN.

Implementation
Wireless Network
• Utilizes LoRaWAN for low-energy communication.

Wearable Sensors
• Integrates GPS modules (e.g., NEO-6M) for tracking.

Cloud Analysis Services
• Employs cloud-based services for data analysis and reporting.

System Architecture
Hardware Components
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


Software
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



References
• LoRa Alliance. "Long Range Wide Area Network". LoRa Alliance
• SigFox. "Sigfox Solutions". SigFox
• Mangalvedhe, N., Ratasuk, R., & Ghosh, A. (2016). "NB-IoT Deployment Study for Low Power Wide Area Cellular IoT". PIMRC.
• Mikhaylov, K., Petaejaejaervi, J., & Haenninen, T. (2016). "Analysis of Capacity and Scalability of the LoRa Low Power Wide Area Network Technology". European Wireless.
• Lauridsen, M., Kovacs, I., Mogensen, P., Sørensen, M., & Holst, S. (2016). "Coverage and Capacity Analysis of LTE-M and NB-IoT in a Rural Area". VTC Fall.
``
