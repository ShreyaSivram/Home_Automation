# In this project, an IoT-based automated lighting system is implemented using Sinric software, an ESP32 microcontroller, a 4-channel 5V SPDT relay module, and push buttons. The ESP32 serves as the central hub, transmitting data to the Sinric platform for remote control via popular virtual assistants such as Alexa or Google Assistant. The relay module facilitates safe switching of multiple lighting fixtures, offering both internet-based control and manual operation through integrated push buttons. This project highlights the integration of IoT technologies into home automation, emphasizing ease of use, flexibility, and enhanced control over residential lighting environments

Connect the circuit in the following way:

ESP32                   Breadboard
D23-                        Relay IN1
D22- 	             Relay IN2
D21-     	             Relay IN3
D27- 	             Push Button 1 (Terminal 1)
D14- 	             Push Button 2 (Terminal 2)
D12- 	             Push Button 3 (Terminal 3)
GND-	             Push Buttons 1,2,3 (Terminal 2)
3.3v- 	             Relay VCC
GND- 	             Relay GND
3.3v- 	             LEDs 1,2,3 Anode
GND-                     Relay COM 1,2,3

Relay                     LED
NO 1-                    LED1 GND
NO 2- 	             LED2 GND
NO3-                      LED3 GND


Create an account on the Sinric platform and add a new device and choose its type to “Switch”.
 Repeat the same for the rest two LEDs.
 Go to Devices, and select all the three LEDs, select “Has tactile button” and click ”Next”.
 Now, type in the correct PIN numbers in the fields, click the Active LOW check box. Go to the next page and fill in the wifi credentials.

Now, the application itself generates the code for the project in a ZIP file, download the ZIP file and make the necessary changes in the code:

In the “bool onPowerState function”, change “state” to “!state” in the 2nd and 4th line like in the picture.

In the “void setupRelays()” function, add another line “digitalWrite(relayPIN, HIGH);

Thus, now you can control the LEDs via SINRIC PRO

To automate the circuit, go to Automation section.
Add automation, give it a name and a description.

Now, configure the actions for eg, at a specific time, fill in the details.
For condition, drag one of the LEDs and configure it to ”OFF” position.
For actions, drag the same LED and configure it to “ON” position.

Repeat the same for the other LEDs and see the LEDs glow for the mentioned time


Download the “Google Home” app and log in.
Create a home, give it a name and address.
Add device => Set up Device => Works with Google => Search for SINRIC PRO
Login to SINRIC PRO account. Now, go to the main page of the application and see if the devices are available on the dashboard.
Now, switch ON/OFF the LEDs to check their working. 








