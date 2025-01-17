# Astama_Detection
This project integrates an ESP32 microcontroller with multiple sensors, including a MEMS INMP441 microphone, to detect and predict asthma in humans. The system captures respiratory sounds, air quality, temperature, humidity, heart rate, and oxygen saturation, which are critical indicators of asthma. The MEMS microphone, placed on the chest, monitors respiratory operations to detect abnormalities in breathing patterns. Real-time data collection and processing are achieved using an RTOS-based approach, ensuring efficient multitasking. The collected data is used to train a machine learning (ML) model on the Edge Impulse platform, enabling the system to predict asthma conditions. The results are displayed on a 1.3-inch OLED screen, and alerts are provided through a buzzer in critical situations.
![image](https://github.com/Saifali4604/Asthma_Detection_on_ESP32_using_ML/blob/main/IMG_20250116_013132.jpg)

## Components Used:
1. ### ESP32 (ESP-WROOM-32):
   The central processing unit that collects sensor data, processes it, and forwards it to Edge Impulse for training the ML model.
2. ### MEMS Microphone (INMP441):
   Monitors respiratory sounds when placed on the chest, enabling the system to detect abnormal breathing patterns indicative of asthma.
3. ### Gas Sensor:
    Measures air quality and pollutants that may trigger asthma.
4. ### DHT11/DHT22 Sensor:
   Captures temperature and humidity, environmental factors that significantly affect asthma conditions.
5. ### MAX30100 Pulse Oximeter:
   Monitors heart rate and oxygen saturation, physiological indicators of asthma.
6. ### 1.3-inch OLED Display (ST7789 Driver):
   Displays vital information such as respiratory patterns, temperature, humidity, heart rate, and asthma detection status.
7. ### Edge Impulse Platform:
   Used to train a machine learning model using collected sensor data for asthma detection.

<p align='center'>
    <img src="./ezgif.com-video-to-gif-converter.gif" alt="drawing" width="800"/>
</p>

## Functionality of the Code:
### Respiratory Monitoring:
   The INMP441 microphone continuously captures respiratory sounds.
The data is processed to identify abnormalities, such as wheezing or irregular breathing patterns.

### Data Collection:
   Sensors collect real-time data on gas levels, temperature, humidity, heart rate, and oxygen saturation.

   
All data is synchronized using RTOS to ensure efficient multitasking.

### Real-Time Operating System (RTOS):
   RTOS manages tasks such as data acquisition, sound processing, and display updates.
High-priority tasks like respiratory monitoring are processed without delay.

### Machine Learning Model:
   The respiratory and environmental data is forwarded to the Edge Impulse platform for training.
The trained model, capable of detecting asthma-related patterns, is deployed on the ESP32 for real-time predictions.

### Prediction and Alerts:
   The ML model analyzes respiratory sounds and environmental data in real-time.
If abnormal patterns or triggers are detected, the buzzer sounds an alert, and the display shows a warning.

### Display Interface:
   The OLED screen displays vital data, including respiratory status, temperature, humidity, heart rate, and asthma detection status.
The interface is intuitive and user-friendly.

### Data Forwarding:
   The ESP32 is connected to Edge Impulse through a provided code interface.
Collected data is uploaded for training and refining the ML model.


# Software Method 1
## python Installation
Download the latest version Python from [https://www.python.org/downloads/] for Windows / linux.

Run the installer and make sure to check the box that says Add Python to PATH during the installation process.

Once installed, restart the Command Prompt and try running:
``` python --version ```

## Node.js Installation
Install Node.js v20 or above on your host computer, using [https://nodejs.org/en/] 
install it selecting the option: Automatic install the necessary

## Edge Impulse CLI
### Windows:

Install WSL on your Windows machine, To install WSL, open PowerShell as an Administrator and run:
``` wsl --install ```


restart the Computer


open PowerShell as an Administrator and run:
``` wsl ```
follow the Linux setup.

## Linux :

```
curl -sL https://deb.nodesource.com/setup_20.x | sudo -E bash -
sudo apt-get install -y nodejs
node -v
```

Let's verify the node installation directory:
```
npm config get prefix
```

If it returns /usr/local/, run the following commands to change npm's default directory:
```
mkdir ~/.npm-global
npm config set prefix '~/.npm-global'
echo 'export PATH=~/.npm-global/bin:$PATH' >> ~/.profile
```

```
sudo apt update && sudo apt install -y build-essential
```

```
make --version
```

Install the CLI tools via:

```
npm install -g edge-impulse-cli
```
[https://docs.edgeimpulse.com/docs/tools/edge-impulse-cli/cli-installation]
[https://docs.edgeimpulse.com/docs/tools/edge-impulse-cli/cli-data-forwarder]
### or Arduino CLI
[https://arduino.github.io/arduino-cli/1.1/installation/]

### Data Forwarding
1. Create a Project in Edge Impulse Platform.
2. click to "Connect your device or development board".
3. Upload the Given Code.
4. close the Arduino IDE.
5. Remove and connect the ESP32 to the Laptop.
6. Open CMD/Power shell/ WSL/ Linux.
7. Run
   ```
    edge-impulse-data-forwarder --frequency 50
   ```
8. Sample is been Uploaded.

# Method 2
If you have issues installing the CLI you can also collect data from fully-supported development boards directly using recent versions of Google Chrome and Microsoft Edge. 


Collecting data from real devices is the first step of any embedded machine learning solution, and to make this even easier we’re adding support for Web Serial to the Edge Impulse Studio.


This means that you can now collect data from any fully-supported development board straight from your browser, without any other tools installed on your computer.


To get started just open the latest version of Google Chrome or Microsoft Edge, go to the data acquisition page in the Studio, and click ’Connect using WebUSB’.


Select your development board, and you’re done.


You can now collect data from any of the built-in sensors, see a visual preview on boards with a camera, and verify your model.

[https://edgeimpulse.com/blog/collect-sensor-data-straight-from-your-web-browser/]
