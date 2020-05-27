# My Experience With Arduino and Circuits By: Justin Brassard

## Day 1: Reflection

Throughout my first day in the module electronics for the rest of us, we discussed various aspects connecting many concepts from programming through GitHub, to creating websites and using various commands to personalize our own website through coding. Generally, I am interested in taking this module as I do have past experience in python and JavaScript. My knowledge on using both of these programs is still at the beginner’s level as I have only taken a couple of courses online outside of school at McMaster University. I would really like to get more involved and improve my programing skills as it is something that has always interested me. I can in fact incorporate these skills in GIS, as this is in fact the path I am choosing to pursue in my future. I enjoy working on computers and I am always willing to expand my skills, hence why I chose to take this course. I also hope to take away various things from this. I hope to gather more computer programming skills as well as to incorporate these skills in the future. Having more introductory knowledge in programming will allow me more experience in order to proceed with my learning in the intermediate level. This will allow me to gain more certification and at the end of it all, who knows, I may just end up going back to school to get another degree in programming if I see it interests me more. This experience will truly allow me to see more then the few perspectives and programming methods that I have already learned. 


**My First Button Circuit**

![Button Circuit](images/IMG_20200520_192045.jpg)

------------------------------------------------------------------------------------------------------------------------------

## Day 2: Results

**Fully-Commented Arduino Sketch**

[Ardruino Sketch DAY 2 RESULTS](https://github.com/inspire-1a03/intersession-2020-JustinBrassard/blob/master/docs/RGB_LIGHT_WITH_THEMO.ino)


**Image of Themistor and RGB LED**


![Second Circuit](/images/IMAGE RGBLED-THEMISTOR.jpg)

This is a simple circuit that uses RGB to power a light and make it switch colours. There is also a second part attached to this. The thermistor measures the room temperature based off the way the program was coded. The thermistor calculates the temperature approximately every 5 seconds. As the temperature increases, the light turns red. As it descends, and gets below 20, it goes blue, an anywhere between 20 and 30 (Fahrenheit), the light will remain a green colour. The part that was challenging about this was combining the two different types of codes. It took various attempts with trial and error in order to know what parts to copy into the void setup and void loop sections in order to make it function properly. This circuit worked relatively well, and all code was very clear, although I had a common anode and therefore had to plug my final wire connecting to the light into the 5V port (Volts) rather than the ground to make it function. 

------------------------------------------------------------------------------------------------------------------------------

## Arduino build-off results

**Fully-Commented Arduino Sketch**

[Ardruino Sketch for the BUILD - OFF](https://github.com/inspire-1a03/intersession-2020-JustinBrassard/blob/master/docs/RGB_LIGHT_THERMI_BUZZ.ino)

**Image of My Circuit**

![Build Off Circuit](/images/IMAGE RGBLED_THERM_BUZZ.jpg)

This product combines the majority of the concepts that we learned throughout the week. It is a device that will signal the user if the temperature in the room is too high, low, or at the right temperature using different sound frequencies and colours to represent each aspect needing to be depicted. The template shown below describes what each of the component’s roles are within this circuit.  Putting this somewhat seeming complex circuit into an easier explanation, the thermistor detects the temperature of the room. Based off the temperature that is detected by this sensor, the RGB LED lights will either be green if the temperature in the room is recorded to be between 20 and 30 Fahrenheit, Red is it above 30, and Blue if it gets below 20. Along with the sensor allowing the light to switch colours, the buzzer would also make different pitched sounds if the temperature went above the required range or below it (20-30 degrees). A higher pitched sound was coded for the temperature above the range and a lower one for below in order to differentiate the two from one another. This could be used in everyday life if your AC unit at home ever breaks down and the temperature gauge cannot detect the temperature anymore. This could be linked to something of this nature in order to signal it to start and stop based off the temperature calculated by the thermistor. In a rarer case, this could be used within a car. This would have to be at a much larger scale, although it could help detect the temperature for the engine of a car. If it overheats, or gets too hot, it would essentially make a sound. In this case, the cold factor could be eliminated as a cold engine just means it has perhaps been sitting for a while. These are some examples of some cases in which this device could be used.

**Components of the Circuit**

This is a table explaining each component within the build off project:

|   Components     | Description |
|------------------|-------------|
|   Thermistor     | Detects the room temperature using a sensor|
|    RGB LED       | Turns different colours based off the temperature in the room (30 + = Red, 20-30 = Green, 20 - = Blue)|
|     Buzzer       | Creates different pitches of sound when the temperature goes above or below the set required|



<iframe width="648" height="365" src="https://www.youtube.com/embed/EZL8S-n6DTc" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

------------------------------------------------------------------------------------------------------------------------------

## Final reflection & summary

Before this week, I had previously come into this module with little experience in Python and JavaScript due to my aspired career path in GIS. Within this program, coding is often used to assist users in creating easier map interfaces to analyze data. By learning the basics of Arduino throughout the week, along with how to build simple circuits, I have expanded my knowledge to learn another platform and connect real life scenarios in application with my circuits. I had a tiny bit of knowledge on the bread board previously, although I had never really applied components such as the Thermistor, or the buzzer to the board before. I loved the fact that this course allowed me to explore and learn to build circuits along with having lots of support from the professor. Having an experienced hand in order to help you not only solve your problem, but understand it is key in being successful especially when it comes to something as complex as programming. I have now learned to completely put together and program a circuit myself by combining various aspects not only through the Arduino board itself, but through code as well. I personally found that this course moved at the perfect pace and allowed me to learn a good level of beginner knowledge in Arduino. Although the challenging part to this was that the new concepts did have to be learned in such a short period of time. Although, consistent feedback and assistance through Microsoft teams was provided to help with this. This was generally an amazing experience, as I expanded my coding knowledge and I hope to take more courses that have a similar style to this one.
