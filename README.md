Gucci-Goobers
=============

This is the repository for the Gucci Goobers, a group of freshman engineers at CU Boulder!

=======
##COLLABORATORS: 
Check out this link and take 20 minutes to learn the basic ins and outs of GitHub...
https://guides.github.com/activities/hello-world/

##Background/Client Info:
  For the Gucci Goobers’ final project, we will be working with Andre from Jacob Springs Farm. A number of problems, or inconveniences, were posed at the farm, such as ensuring the chicken coop is closed at night, measuring the remaining water supply of the farm, cueing the ventilation of the greenhouse, etc. We decided, however, on working with the electric fence, which keeps Andre’s livestock in one area. The problem with the electric fence is that it can be grounded very easily (i.e grass touching the fence can cause it to lose functionality). Many of the animals are very obedient, and once they’re shocked once they will not go near the fence again. However, some animals (such as the goats and sheep) are a little more persistent, and will test the fence regularly. If there is no shock emitted by the fence, the goats and sheep will go right through it. The goal of our project is to create a voltage detector, which notifies Andre whenever the fence is shorted out, grounded, or loses charge for any reason. We are working to be able to detect where the fence is grounded in relation to a fixed point. This would save the farmer a great deal of time. Without detecting the location of the shortage, the farmer must walk the entire perimeter of his fence. This is not ideal, and we are aiming to save the farmer as much time as possible. We believe this could benefit livestock farmers at an international level – saving them time and money, and, in turn, allowing them to be more productive.


##Design Requirements:
Sensor must be able to withstand a voltage of 12000 V.
Sensor must be able to measure a currents ranging between 0 and 5 Amps of pulsing current.
Device must be able to transmit signal from one corner of the fence to another, and also to the “mother” Arduino. Corners can be between 100 and 2000 feet apart depending on the configuration of the fence.
Arduino must be able to send an sms to the clients phone at least once a day and still remain under the budget.
Device must be able to determine the location of short.
Device must be able to withstand wind, rain, heat, snow and frost.
Device must have a power source that can supply 5 volts to power the Arduino.
Production cost must be under 375 Dollars.



##Design Alternatives/Brainstorming
- Measuring current/voltage
  - Standard voltmeter or multimeter: The quick pulses of an electric fence would damage these.
  - Specialized voltmeter for an electric fence: This was upward of 70$ and not within budget since our project requires four of them.
  - Non-invasive current sensor(5 Amps maximum): This would be unlikely to be damaged because it does not directly touch the fence and having a sensor that works with low current would give a more accurate reading compare to sensor that read up to 30 Amphere.
- Minimizing search area: When a fence becomes grounded, someone must walk around the entire fence in search of what is causing the problem. We wanted to minimized the area that person has to search.
  - Algorithim: An idea was to derived an algorithim that could tell where the grounding issue occured between two sensors.
  - Four sensors: Putting four sensors along the fence would allow us to determine beetween what two sensors the grounding occured at. That way only one fourth of the fence needs to be searched for problems.
- Power source
  - Electric fence: Early ideas were about drawing power from the electric fence itself, however it was not feasible for this project because when the fence becomes grounded, the electronics would lose their power supply.
  - Solar panel: Solar panels would be environentaly friendly but could be unreliable at night and on cloudy days.
  - Solar panel and battery: Having a solar panel charge a battery would make a much more reliable power source.
- Sending notifications
  - Wi-Fi shield: We came to the revelation that using Wi-Fi is not thinking globally because farms to not typically have Wi-Fi. Even in Andre’s case there is no Wi-Fi connection at the actual location of the electric fence.
  - GMS shield: That would require obtaining a network connection, which is not within our budget
  - Xbee: Can communicate between multiple arduinos and cheeper ones can communicate 300 feet, which would work well for what we need.
  

##Interactions with Client:
###Questions for Andre:

1.	What Kind of Battery powers the fence?

2.	What are the lengths of each side of the fence? 

3.	What is the gauge of the wire? 

4.	How often does the fence go down? 

5.	What is the voltage applied to the fence? 

6.	Do you know what the average current is in the wire? 

###Andre’s Answers

1.	I have four fence chargers: two of my fence chargers are plug in 110 V two of them are solar with 6V batteries 

2.	I constantly reconfigure fences depending on pasture arrangement lengths could be anywhere from 100 to 2000 feet

3.	Wire is variable Perimeter wire is usually 12 or 14 gauge galvanize steel but sometimes is aluminum probably wire is 		usually 6 to 15 strands of very thin gauge stainless steel wire 

4.	Fence can be discharged by a short as often as once a day and as rarely as once a month depending on the animals and 		their attitude

5/6.	Sure what the voltage and current is I have a Zareba 6 joule energizer, a to acre pioneer and two others. My 			understanding is it’s very high voltage very low current short duration bursts. You could probably look up the specs. If 	you need the model numbers I can give them to you. (According to the specs of these energizers we need something that can 	withstand 12000 volts and measure in a range of 0-5 amps.)

>>>>>>> origin/master
