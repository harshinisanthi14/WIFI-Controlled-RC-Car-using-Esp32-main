# URL-Controlled-RC-Car-using-Esp32
URL Controlled RC Car using Esp32

In this project, i created a WiFi-controlled RC car using an ESP32 microcontroller. Here's a brief explanation of how it works:

Components Used:
1. ESP32 Microcontroller: This will act as the brain of the project. It has built-in WiFi, which allows it to connect to your local network and listen for HTTP requests from your phone or computer.
2. Motor Driver (L293D): This controls the DC motors for the car, allowing you to move it forward, backward, left, right, or stop. The ESP32 sends signals to the motor driver to control the direction and movement of the motors.
3. DC Motors: These are connected to the motor driver. They control the movement of the wheels on the car chassis.
4. Wires and Breadboard: These are used for connecting the ESP32 to the motor driver and motors.
5. Car Chassis: This is the physical body of the car where the motors and ESP32 are mounted.

How it Works:
1. WiFi Connection: The ESP32 connects to your WiFi network using the provided SSID and password. Once connected, it starts a web server, which listens for incoming HTTP requests.

2. HTTP Requests: The ESP32 listens on a specific IP address and port (typically port 80). When you open the browser and type `http://<ESP32_IP>/forward`, the ESP32 receives this HTTP request and interprets it.
   - /forward: The car moves forward.
   - /backward: The car moves backward.
   - /left: The car turns left.
   - /right: The car turns right.
   - /stop: The car stops moving.

3. Motor Control: Based on the HTTP request, the ESP32 sends corresponding control signals to the motor driver:
   - Move Forward: Sends a signal to the motors to rotate in a direction that moves the car forward.
   - Move Backward: Reverses the motor direction to move the car backward.
   - Turn Left/Right: Controls one motor to rotate forward and the other to rotate in reverse to turn the car left or right.
   - Stop: Stops both motors to halt the car.

4. Command Response: After the motor control command is sent, the ESP32 sends back an HTTP response confirming the command was received (e.g., “Command Received”). This lets you know that the car is responding to your input.

Steps to Control the Car:
1. Upload the code to your ESP32 using the Arduino IDE.
2. Connect the ESP32 to your WiFi network.
3. After a successful connection, note down the ESP32's IP address (printed on the Serial Monitor).
4. Open a browser on your phone or computer and type the ESP32's IP address followed by the command (e.g., `http://192.168.43.48/forward`).
5. The motors will respond to your commands, and the car will move according to your input.

How to Use:
1. Open Browser: You can use any device that is connected to the same WiFi network (smartphone, laptop, etc.).
2. Type the URL: To control the car, you enter commands like `http://<ESP32_IP>/forward`, `http://<ESP32_IP>/backward`, etc., in the browser.
3. Control the Car: The car moves based on the commands you send.

Applications and Use Cases:
- Basic RC Car: This setup can be used as a basic WiFi-controlled RC car.
- Automation Projects: Integrating this with other sensors (e.g., ultrasonic sensors for obstacle avoidance) can make the car autonomous.
- IoT Learning Projects: This is a great project to learn about WiFi-based control and IoT integration with microcontrollers.

Possible Improvements:
- Voice Control: You can integrate voice commands using Google Assistant and IFTTT to control the car with your voice.
- Mobile App: You can create a simple mobile app (using Flutter or React Native) to control the car more easily than using a web browser.
- Camera Integration: You can add a camera to stream live footage from the car to enhance the remote driving experience.

This project provides a basic foundation for creating IoT-based, remote-controlled devices using WiFi and the ESP32.
