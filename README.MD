Welcome to the JArduino project, powered by ThingML (www.Thingml.org)!

Browse the dist folder to get the latest JArduino distribution, which you can import as an Eclipse project. 
People interested in the concepts behind JArduino can read our paper "MDE to manage communications with and between resource-constrained systems" (http://www.fleurey.com/franck/uploads/Main/Models2011a.pdf). 
If you are more into the code, just try it out for real!

	$ git clone https://github.com/SINTEF-9012/JArduino.git


Before using JArduino, please make sure your Arduino board contains the JArduino firmware:

	1- Copy the JArduino folder (located in the distribution in org.sintef.jarduino.samples/arduino) into /libraries/

	2- Launch your Arduino environment

	3- File -> Examples -> JArduino -> JArduino firmware. It should open an Arduino program that you should upload to your board using the normal Arduino procedure.

	4- Your Arduino board is now ready for Jarduino. You can exit the Arduino environment forever and launch Eclipse. Just run the Java/JArduino program.


To test samples using the current version of JArduino (requires Maven + the Arduino board connect on the serial port of the PC):

	$ cd JArduino
	
	$ mvn clean install
	
	To run some examples without IDE
	
	$ cd jarduino.samples

	$ mvn exec:java -Dexec.mainClass="org.sintef.jarduino.gui.JArduinoGUI"
	
	Replace "org.sintef.jarduino.gui.JArduinoGUI" with your own main class


Please read our 2-minute tutorial at https://github.com/SINTEF-9012/JArduino/wiki/2-Minute-Tutorial

The ThingML/JArduino team.


Ethernet usage :

    1 - Instead of JArduino folder, copy the JArduinoEthernet folder to Arduino IDE librairies folder

    2 - Launch Arduino environment

	3- File -> Examples -> JArduinoEthernet -> JArduino firmware. It should open an Arduino program that you should 
		
		4- if you have associated the MAC address of your shield to a static IP in your router, please update the MAC address in the firmware (line 84). Otherwise, DHCP should manage everything.

		5- upload to your board using the normal Arduino procedure.

	6- Your Arduino board is now ready for JarduinoEthernet. You can exit the Arduino environment forever and launch Eclipse. Just run the Java/JArduino program.

	7 - JArduinoEthernet does not need  JArduino.serial maven dependency, don't forget to remove it if you want to use JArduino from an Android application for instance.

	8 - Can can now sse JArduino constructor to configure the IP of your device and don't forget to set the communication module to ethernet like bellow

		JArduino arduino = new BlinkEthernet(ip, JArduinoCom.Ethernet)

	9 - To run a sample, just:
		mvn clean install exec:java -Dexec.mainClass="org.sintef.jarduino.examples.basic.BlinkEthernet" -Dexec.args="<IP-address-of-Arduino-board>"

	    

