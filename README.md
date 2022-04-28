# AUTO-MEASURE-SOIL-MOISTURE-CONTENT
# 1.1	Abstract
This is simple project which will helps people to know moisture content of their soil (i.ethe level of water contained in their soil).
Here we use electronics devices which are able to communicate with person to tell the soil condition
FC-28 soil moisture sensor is device which plugged into the soil to measure the level of water in the soil
Then it send data to the Arduino board to be analyzed according to instruction given by person 
Then after knowing soil condition the extra tools can be commanded by Arduino signal
To pour water in that soil if its water level is low or stop pouring water if soil is getting enough water
But here we used buzzer to inform that the level of water in soil is less
And we used liquid crystal display to show readings of soil condition
The extra tools spoken can be like water pump, pipes in order to make automatic irrigation such as in garden, crops farming etc
So this simple controlling machine is operated by low power of 5v dc
And it achieve greater work.
# 1.2	Problem statement
All crops need water for certain level in order to grow well and we know sometime the time of sun can be too long  and cause soil water content to be low which can result to the drying of crops planted in that soil
So to solve this question the irrigation technic was established but it is difficult to be there always in order to see if water in soil reduced or if it is enough 
Especial in land which is far away from where people live or in garden located in cities we cannot get a person who can stand there day and night to check soil condition.
As engineering student we thought about that issue and we design a system which will helps us to know soil condition without reaching there 
We used electronic devices which will give us exact answers about if soil is dray or wet
Buzzer is there to tells us that soil water content is low then we can take decision of pouring water in it.
  
# BLOCK DIAGRAM
![image](https://user-images.githubusercontent.com/103899944/165777665-e69046d1-a8fc-4846-926f-4092ffd5bacd.png)
# Arduino uno source code for this system
#include<LiquidCrystal.h>

const int rs = 12, en = 11, d4 = 5, d5 = 4, d6 = 3, d7 = 2;

LiquidCrystallcd(rs, en, d4, d5, d6, d7);

int analogdata=A0;

int buzzerpin=8;

int value=0;

int threshold=70;

void setup(){

pinMode(8,OUTPUT);

pinMode(A0,INPUT);

lcd.begin(16, 2);

Serial.begin(9600);

}

void loop() {

value=analogRead(A0);

value=map(value,0,1023,0,100);

if(value>threshold){

lcd.print("SOIL IS GETING DRAY");

digitalWrite(8,HIGH);

}

else{

lcd.print("SOIL GET ENOUGH WATER");

digitalWrite(8,LOW);

 }
 
delay(500);

# RUNNING CIRCUIT IN PROTOUS
![image](https://user-images.githubusercontent.com/103899944/165777816-70daf6eb-30e2-4c38-8a5d-3f725e1e0d95.png)
# Image in fritzing
 ![image](https://user-images.githubusercontent.com/103899944/165778286-009adb3f-7202-4bd0-b1ec-7a0b53aebbc1.png)

