Data_over_sound_Chirp

IOT Protocol Stack Design using Communication over sound.

Data-over-sound presents a compelling solution for many device-to-device connectivity applications, particularly for use cases that require frictionless,low cost connectivity with nearby devices. 

We implemented CHIRP in raspberryPi using Python programming language.

1. First of all we need to install the SDK’s dependencies by this command

sudo apt-get install python3-dev python3-setuptools portaudio19-dev libffi-dev libsndfile1

2. Then install the CHIRP SDK directly from PyPi

pip3 install chirp sdk

3. To configure the SDK we need to create .chirprc file in the Home directory with three instruction set i.e. app_key, app_secret, and app_config

Implementing IOT Framework

1. The Data is being collected through various sensors along with the timestamp.
2. A devices randomly selects a number between 0-6 which becomes its channel Id.
3. The Data is being received by all other channels and sent by the one generated channel.
4. This data is converted into Python dictionary,afterward converted into json string using JSON API.
5. This JSON string is converted into byte stream also termed as serialization.
6. As we are using Ultrasonic-multi channel protocol which transfers 7 byte data at a time, so we are dividing the byte stream stream into 7 byte fragments for transferring it.
7. These fragments are now transferred using Chirp to all other receiver.
8. After receiving data through various channels, it creates different JSON files which appends the  received data in the existing file after converting the byte stream received to json string.
9. At last these JSON files are uploaded to Cloud.


For further details refer to Report.pdf



