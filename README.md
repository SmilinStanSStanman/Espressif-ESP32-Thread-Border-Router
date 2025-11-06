[SP32-C6 (OpenThread Radio Co-Processor - RCP)]

GitHub project for OpenThread Border Router:
https://github.com/espressif/esp-idf/tree/master/examples/openthread/ot_rcp

1.- Download the ESP-IDF Windows Installer from: https://dl.espressif.com/dl/esp-idf/

2.- Run the downloaded file "esp-idf-tools-setup-offline-5.4.2.exe" and install it.

3.- Open the CMD with preloaded paths created by the Espressif installation.

4.- Navigate to "C:\Espressif\frameworks\esp-idf-v5.4.2\examples\openthread\ot_rcp"

5.- Run the following commands in the CMD window:
    idf.py set-target esp32c6
    idf.py build

6.- Connect the ESP32C6 to the PC.

7.- Run the following command in the CMD window:
    idf.py flash

[ESP32-C6 SCHEMATIC]

https://github.com/SmilinStanSStanman/Espressif-ESP32-Thread-Border-Router/blob/main/XIAO-ESP32-C6.png

[ESP32-S3 (OpenThread Border Router)]

1.- Clone the Github repository for the Border Router project. In the CMD window execute:
    cd C:\\Espressif\\frameworks\\esp-idf-v5.4.2
    git clone --recursive https://github.com/espressif/esp-thread-br.git

2.- In the CMD window execute:
    cd C:\\Espressif\\frameworks\\esp-idf-v5.4.2\\esp-thread-br\\examples\\basic_thread_border_router
    idf.py menuconfig

3.- This menu will open. Follow these steps:

Navigate to:

ESP Thread Border Router Example >>> Border router board type (Border router dev kit) >>> Standalone dev kits

4.- After selecting these options, you return to the main menu "ESP Thread Border Router Example." Go to the "Board Configuration" option and configure the TX and RX pins as follows:

5.- Press ESC to go back to the "ESP Thread Border Router Example" menu. Go to "Border router RCP target (ESP32-H2)" and select ESP32-C6.

6.- Back in the "ESP Thread Border Router Example" menu, activate the following two options:
    Enable the automatic start mode in Thread Border Router
    Enable the web server in Thread Border Router

7.- Press ESC to go back to the "Top" menu. Go to "Example Connection Configuration." Enter your WiFi network name under "(myssid) WiFi SSID" and your WiFi password under "(mypassword) WiFi Password."

8.- Press "S" to save the configuration, then press "Q" to exit the menu.

9.- In the CMD window, run:
    idf.py build

10.- Connect the XIAO ESP32-S3 to the PC. In the CMD window, run:
    idf.py flash monitor

[ESP32-S3 SCHEMATIC]

[CONNECTION BETWEEN ESP32-S3 BORDER ROUTER AND ESP32-C6 RADIO CO-PROCESSOR]

GPIO44 (RX) pin of the XIAO ESP32-S3 Border Router to the TX pin of the XIAO ESP32-C6 (RCP)
GPIO43 (TX) pin of the XIAO ESP32-S3 Border Router to the RX pin of the XIAO ESP32-C6 (RCP)
GND pin of the ESP32-S3 Border Router to the GND pin of the XIAO ESP32-C6 (RCP)
5V pin of the ESP32-S3 Border Router to the 5V pin of the XIAO ESP32-C6 (RCP)
