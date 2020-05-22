# My Experience With Arduino and Circuits By: Justin Brassard
<!--
Welcome to your project page for Electronics for the Rest of Us. You'll use this page to describe and showcase your work throughout the module. 
A place for each deliverable has been created below for you in this markdown document. 
Note that comments (such as this) will not appear in the final markdown document (which you can view with the "Preview" button).
-->


## Day 1: Reflection

Throughout my first day in the module electronics for the rest of us, we discussed various aspects connecting many concepts from programming through GitHub, to creating websites and using various commands to personalize our own website through coding. Generally, I am interested in taking this module as I do have past experience in python and JavaScript. My knowledge on using both of these programs is still at the beginner’s level as I have only taken a couple of courses online outside of school at McMaster University. I would really like to get more involved and improve my programing skills as it is something that has always interested me. I can in fact incorporate these skills in GIS, as this is in fact the path I am choosing to pursue in my future. I enjoy working on computers and I am always willing to expand my skills, hence why I chose to take this course. I also hope to take away various things from this. I hope to gather more computer programming skills as well as to incorporate these skills in the future. Having more introductory knowledge in programming will allow me more experience in order to proceed with my learning in the intermediate level. This will allow me to gain more certification and at the end of it all, who knows, I may just end up going back to school to get another degree in programming if I see it interests me more. This experience will truly allow me to see more then the few perspectives and programming methods that I have already learned. 


**My First Button Circuit**

![Button Circuit](images/IMG_20200520_192045.jpg)

## Day 2: Results

**Fully-Commented Ardruino Sketch**


Code for Themistor and RGB LED
------------------------------------------------------------------------------------------------------------------------------

/*
Adafruit Arduino - Lesson 3. RGB LED
*/
/*
 * Inputs ADC Value from Thermistor and outputs Temperature in Celsius
 *  requires: include <math.h>
 * Utilizes the Steinhart-Hart Thermistor Equation:
 *    Temperature in Kelvin = 1 / {A + B[ln(R)] + C[ln(R)]3}
 *    where A = 0.001129148, B = 0.000234125 and C = 8.76741E-08
 *
 * These coefficients seem to work fairly universally, which is a bit of a
 * surprise.
 *
 * Schematic:
 *   [Ground] -- [10k-pad-resistor] -- | -- [thermistor] --[Vcc (5 or 3.3v)]
 *                                               |
 *                                          Analog Pin 0
 *
 * In case it isn't obvious (as it wasn't to me until I thought about it), the analog ports
 * measure the voltage between 0v -> Vcc which for an Arduino is a nominal 5v, but for (say)
 * a JeeNode, is a nominal 3.3v.
 *
 * The resistance calculation uses the ratio of the two resistors, so the voltage
 * specified above is really only required for the debugging that is commented out below
 *
 * Resistance = PadResistor * (1024/ADC -1)  
 *
 * I have used this successfully with some CH Pipe Sensors (https://www.atcsemitec.co.uk/pdfdocs/ch.pdf)
 * which be obtained from https://www.rapidonline.co.uk.
 *
 */

#include <math.h>

#define ThermistorPIN 0                 // Analog Pin 0

float vcc = 4.91;                       // only used for display purposes, if used
                                        // set to the measured Vcc.
float pad = 9850;                       // balance/pad resistor value, set this to
                                        // the measured resistance of your pad resistor
float thermr = 10000;                   // thermistor nominal resistance

float Thermistor(int RawADC) {
  long Resistance;  
  float Temp;  // Dual-Purpose variable to save space.

  Resistance=pad*((1024.0 / RawADC) - 1);
  Temp = log(Resistance); // Saving the Log(resistance) so not to calculate  it 4 times later
  Temp = 1 / (0.001129148 + (0.000234125 * Temp) + (0.0000000876741 * Temp * Temp * Temp));
  Temp = Temp - 273.15;  // Convert Kelvin to Celsius                      

  // BEGIN- Remove these lines for the function not to display anything
  //Serial.print("ADC: ");
  //Serial.print(RawADC);
  //Serial.print("/1024");                           // Print out RAW ADC Number
  //Serial.print(", vcc: ");
  //Serial.print(vcc,2);
  //Serial.print(", pad: ");
  //Serial.print(pad/1000,3);
  //Serial.print(" Kohms, Volts: ");
  //Serial.print(((RawADC*vcc)/1024.0),3);  
  //Serial.print(", Resistance: ");
  //Serial.print(Resistance);
  //Serial.print(" ohms, ");
  // END- Remove these lines for the function not to display anything

  // Uncomment this line for the function to return Fahrenheit instead.
  //temp = (Temp * 9.0)/ 5.0 + 32.0;                  // Convert to Fahrenheit
  return Temp;                                      // Return the Temperature
}


int redPin = 11;
int greenPin = 10;
int bluePin = 9;

//uncomment this line if using a Common Anode LED
//#define COMMON_ANODE

void setup()
{
  Serial.begin(115200);
  pinMode(redPin, OUTPUT);
  pinMode(greenPin, OUTPUT);
  pinMode(bluePin, OUTPUT);  
}

void loop()
{
  float temp;
  temp=Thermistor(analogRead(ThermistorPIN));       // read ADC and  convert it to Celsius
  Serial.print("Celsius: ");
  Serial.print(temp,1);                             // display Celsius
  //temp = (temp * 9.0)/ 5.0 + 32.0;                  // converts to  Fahrenheit
  //Serial.print(", Fahrenheit: ");
  //Serial.print(temp,1);                             // display  Fahrenheit
  Serial.println("");                                  
  delay(1000);                                      // Delay a bit...

  if(temp > 30){
  setColor(255, 0, 0);  // red
  }
  else if(temp > 20 & temp < 30){
  setColor(0, 255, 0);  // green
  }
  else {
  setColor(0, 0, 255);  // blue
  }
}



void setColor(int red, int green, int blue)
{
  #ifdef COMMON_ANODE
    red = 255 - red;
    green = 255 - green;
    blue = 255 - blue;
  #endif
  analogWrite(redPin, red);
  analogWrite(greenPin, green);
  analogWrite(bluePin, blue);  
}


------------------------------------------------------------------------------------------------------------------------------

Image of Themistor and RGB LED







<!--
Upload your fully-commented Arduino sketch from your final Day 2 build task--a thermometer connected to an RDB LED--into your GitHub repository.
Provide a short (~150 words) summary of your work on this circuit:
- How does your device work?
- What was challenging? 
- What worked? What didn't? 
- Be sure to link to your code (in your GitHub repository) in the text of your response.
-->

## Arduino build-off results
<!--
Upload your fully-commented Arduino sketch from the final product of your Arduino build-off into the top-level of your module GitHub repository.
In ~300 words, provide a final device description and product pitch: 
- What does it do? Use a table (created in markdown) to list and describe the features. You can use the template provided below. 
- Describe briefly how it works.
- How could it be used in everyday life (or maybe just in rare cases)? 
- Be sure to link to your code (in your GitHub repository) in the text of your response.
- Include a snippet of code using the ``` ``` characters to display the code properly. 
Finally, record a short (30 second) video of a 'product pitch' for your device. 
- Upload the video to Youtube, and use the sample code below to embed your video.
-->


<!--
Below is a general markdown table template. 
You can find more information at these links: 
- https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet#tables

-->
| Feature | Description | Other Notes |
|---------|-------------|-------------|
|         |             |             |
|         |             |             |
|         |             |             |
|         |             |             |


<!--
Below is an example of embedding a YouTube video in a markdown document for use in GitHub pages. 
Note that this video won't show when previewing the document in GitHub--it only works on the GitHub pages webpage. 
- Once your YouTube video is uploaded, right click and select ```<> Copy embed code```. 
- You can paste this code directly into your markdown document. 
- Note that you may want to adjust the width and height parameters to make it fit well in your webpage
-->

<iframe width="789" height="444" src="https://www.youtube.com/embed/dQw4w9WgXcQ" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>


## Final reflection & summary
<!--
In ~300 words:
- Summarize your experience in this module. What you learned, what you liked, what you found challenging.
- Reflect upon your learning and its relevance in your life.
-->
