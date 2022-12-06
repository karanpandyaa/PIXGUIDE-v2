# PixGuide
**Abstract**:

The main motive of this device is to help the two-wheelers navigate without having to use different applications or mounting their mobile phones or other expensive machines on the vehicle. The significant finding from this project is the voice pack utilization for navigation. Our device can be used in bright sunlight as well as in the dark. It is compact and user-friendly. Our project has a benefit that we do not need any application for navigation. The Google APIs that are used to make a navigation system are costly; hence, we have made use of voice packs to make navigation device cheap. It could become an inbuilt function of Google Maps, and multiple devices could use it without needing to make separate applications for navigation.

**Working**:

The major breakthrough in this working is that we are using the google voice packs to get the navigation system data from google maps. All the command in google maps has a voice(.mp3) file linked with it which is played whenever the command is activated.We made a voice pack for our own having frequency linked with each command.The Bluetooth receiver receives the frequency and shows the linked command animation on the LED matrix.

**Design**:
* There is an additional hood to make the LED matrix visible in intense sunlight.
* The Garmin Quarter mount is easy to use and compatible with all types of cycle handlebars.
* The design has a slot at the front for a torch.
* The hood is sliding using a rolling pair behaving like a sliding pair. To lock the hood at the top position, we slide a small rectangular piece at the lower end of the hood into a small hole of similar dimensions made in the upper end of the body.
* The Quarter turn Garmin mount that we used for the mounting system has two components a plate and a mount.
* The plate rotates on the mount, after a quarter turn the plate locks on to the mount. It is one of the most efficient and easy to use mounting mechanism.
![](https://i.imgur.com/gxeJAN3.png)
![](https://imgur.com/bSbqIrf.png)


**Features**
A turn by turn navigation device which syncs with Google Maps and runs without any external app.
Visible in the dark as well as in daylight.
Compact, portable, and easy to handle device which works on 500 mAh 3.7 V Li-ion battery.


**Animation**:
These are few examples of the animations that we made for various commands on LED 8x8 Matrix.
![](https://i.imgur.com/2tQDoAx.png)


**Hardware**:
* Operational amplifier circuit
* Arduino Pro Mini
* MAX7219(8x8 LED matrix)
* Li-ion battery
* Bluetooth audio receiver

**Features**:
* It utilizes all the features of Google Maps like re-routing, distance measurement, etc.
* Highly cheap product
* It is water-resistant
* Replaces the use of smartphones for navigation and helps to save battery for important uses.
* Protects phone from external damages or unintended fallings from two-wheelers.
* No custom App installation.
* Clear display in both day and night
* It is compact, portable, and easy to use.
* Can be even extended for four-wheeled vehicles.

**Hardware**:

![](https://imgur.com/6odNtt3.png)
![](https://imgur.com/AcNYOoe.png)

The hardware consists of an operational amplifier circuit which is used to amplify and offset the signal from the Bluetooth audio receiver so that the Arduino Pro Mini can read it.

The offset voltage is 2.5 Volts, and the gain of the amplifier was set up using the readings from CRO.
The op-amp is powered using 5 Volts.

There is a 3.7 to 5V boost converter circuit used to power the pro mini, op-amp, and the LED matrix. The DIN, CS, CLK pins of MAX7219(8x8 LED matrix) is connected to the 4th, 5th, 6th pin of Arduino Pro Mini respectively. The Bluetooth audio receiver works on 3.7 v and is connected in parallel to a Li-ion battery.



**Our Code**:

The code is written in Arduino. We have used SPI and MaxMatrix library. Arduino reads the values from the Bluetooth receiver and displays the animations in the matrix. Our code uses the pulseIn function of Arduino which reads a pulse (either HIGH or LOW) on a pin. For example, if the value is HIGH, pulseIn() waits for the pin to go from LOW to HIGH, starts timing, then waits for the pin to go LOW and stops timing. 

The PulseIn function returns the length of the pulse in microseconds or gives up and returns 0 if no complete pulse was received within the timeout. The code has a self formulated mathematical function which finds the frequency (using the time duration) associated with the signal received by the Bluetooth receiver. According to the frequency ranges associated with the signal, Arduino assigns a specific animation that is displayed on the LED matrix. This animation guides in the navigation of 2 wheelers. 

To reduce the time complexity of the code, we have used Switch case statements. When a command from Google Maps is sent in the form of signal to Arduino, it checks which condition it indicates and which range it falls into. Then it executes the code inside the condition and displays the required direction as the output.

**Google Voice Packs Method**:

This is the unique feature of this project. As the other devices or applications use the costly Google API to use the navigation feature of Google Maps, they become costly. Making a navigation app is complicated and requires at least a basic knowledge of how to build an app. There is an alternate way that saves all that effort and is quite simple rather than building a complete application. Google uses voice packs that give instructions like “Head Right” and other similar instructions. All these media files are stored in the Google Maps folder in our devices. So the basic idea is to make our voice pack and paste it there and use it through Google Maps.

Now to create a voice pack, all we need to do is to make mp3 files of what signal we need and give it the same name as those given to commands in voice pack. While the Google Maps are navigating it simultaneously keeps playing the corresponding instruction mp3 files. Now since it has to speak in the language that user wants, they have made voice packs and hence if we keep the same file names and change the voice pack setting from maps to our customized folder it will perform according to our commands.

For this device, we have chosen square waves of different frequency, and for every range of frequency, we have set different instructions. For example, if we have coded 90 Hz frequency for a right turn, then as soon as that frequency is generated, the Bluetooth module receives frequency and the microcontroller checks in which range the frequency is and accordingly displays the animation for right turn on the LED matrix. Different devices can use this for different purposes as it does not require any additional cost for making this process work. So this method has various applications and also it is much easier to implement.



**Applications**:
* This device can be used for various vehicles and can be optimized to be used as an indicator for the direction when attached behind the cycle. 
* For the safety of expensive devices that we generally use for navigation 
* To avoid accidents that are caused due to earphones 



