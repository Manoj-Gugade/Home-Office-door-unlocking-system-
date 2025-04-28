System Overview

**Master Device (ESP32-CAM)**

Acts as the primary interface and camera unit.

Hosts a web server displaying a camera feed and control buttons.

Streams video (QVGA, Grayscale, MJPEG) for a fixed duration (2 minutes) when activated.

Streaming can be initiated via the web interface or a physical button press.

Controls an LED locally (simulating an unlock mechanism).

Sends HTTP requests to the Slave device to trigger its buzzer.

Listens for HTTP requests from the Slave device (e.g., unlock requests).

Uses esp_camera, WiFi, WebServer, HTTPClient, ArduinoJson, and FreeRTOS features.

**Slave Device (ESP32 WROOM)**
Acts as a secondary control/notification unit.

Hosts a simple web server for status display and manual buzzer activation.

Controls a buzzer, typically activated remotely by the Master for a short duration (1 second).

A physical button sends an HTTP request to the Master (e.g., to request an unlock).

Uses WiFi, WebServer, HTTPClient, ArduinoJson, and FreeRTOS features.
