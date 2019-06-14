# DHT11SensorAzure-IoT-hub-Rasp

Hardware components:
Raspberry Pi 3
DHT11 Temperature & Humidity Sensor (3 pins)

Overview of DHT11 Sensor:
The DHT11 sensor can measure relative humidity and temperature with the following specifications:

Temperature Range: 0-50°C
Temperature Accuracy: ±2 °C
Humidity Range: 20-90% RH
Humidity Accuracy: ±5 %

How DHT11 Sensor works:
The DHT11 sensor comes with a blue or white colour casing. Inside this casing we have two important componentswhich help us to sense the relative humidity and temperature. The first component is a pair of electrodes; the electrical resistance between these two electrodes is decided by a moisture holding substrate. So the measured resistance is inversely proportional to the relative humidity of the environment. Higher the relative humidity lower will be the value of resistance and vice versa.  Also note that Relative humidity is different from actual humidity. Relative humidity measures the water content in air relative to the temperature in the air.
The other component is a surface mounted NTC Thermistor. The term NTC stands for Negative temperature coefficient, for increase in temperature the value of resistance will decrease

Hardware components:
•	Raspberry Pi 3
•	DHT11 Temperature & Humidity Sensor (3 pins)
Procedure:

Step1 :
Download the sample Python project from https://github.com/Azure-Samples/azure-iot-samples-python/archive/master.zip and extract the ZIP archive

Step2 :
Installing the Adafruit DHT11 library on Raspberry Pi:
•	Enter the four command lines one by one on the terminal to install the DHT library:
pi@raspberrypi:~ $ git clone https://github.com/adafruit/Adafruit_Python_DHT.git 
pi@raspberrypi:~ $ cd Adafruit_Python_DHT
pi@raspberrypi:~ $ sudo apt-get install build-essential python-dev 
pi@raspberrypi:~ $ sudo python setup.py install

Step3 :
Before continuing any further I do recommend testing the DHT11 sensor is working correctly.
This can quickly be done by changing some of the lines of the file simpletest.py in the location: /Adafruit_Python_DHT/examples/
Below are the areas of the file which require changing and the values required (e.g. pin = 4) to enable the test script to work:
uncomment the Pin=4 line and put comment in Beaglebone pin.change Dht22 to Dht11.

Step4 :
Now, In a local terminal window, navigate to the root folder of the sample Python project. Then navigate to the iot-hub\Quickstarts\simulated-device folder

step5 :
Open the SimulatedDevice.py file in a text editor of your choice.
Replace the value of the CONNECTION_STRING variable with the device connection string
and also add the code of simpletest.py in it and Then save your changes to SimulatedDevice.py file.(or create a new file and copy the code in it)
Step6 :
In the local terminal window, run the following commands to install the required libraries for the simulated device application:
pip install azure-iothub-device-client

Step7 :
In the local terminal window, run the following commands to run the simulated device application:
python <urfilename>.py
Step6 :
Read the telemetry from your hub
•	The IoT Hub CLI extension can connect to the service-side Events endpoint on your IoT Hub. The extension receives the device-to-cloud messages sent from your simulated device. An IoT Hub back-end application typically runs in the cloud to receive and process device-to-cloud messages.

•	Run the following commands in Azure Cloud Shell, replacing YourIoTHubName with the name of your IoT hub:

>>az iot hub monitor-events --hub-name YourIoTHubName --device-id <urdevicename>





