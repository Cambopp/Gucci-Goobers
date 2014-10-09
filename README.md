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
	In the course of our design process there were a seemingly endless amount of ideas that came and passed. One of the first problems that we set out to solve was a way to measure the current or voltage on an electric fence in a cheap and accurate way.  Quickly it became apparent that a standard electrician’s voltmeter or multi-meter would not work on an electric fence due to the short duration of pulses that would damage this kind of equipment.  When looking at voltmeter that are made for electric fences run at a cost upward of 70 dollars.  That wasn’t at all within our budget, especially because we are looking to have as many as four measuring stations.   Our next idea came from the help of our professor.  A non-invasive current senor measures the magnetic field created by the electricity without actually touching or interfering with the fence itself.  They are cheap, about ten dollars, and effective as well as being unlikely to be damaged by the fence.  However we hit a snag with that idea which was that electric fences operate at low currents, as low as under one amp.  The common sensors we were finding operated at 30 amps or more.  Eventually we were able to find a senor that measures a maximum of five amps.  
	In addition to simply detecting if an electric fence is grounded we hope to make the resolving of the problem itself more time efficient.  When a fence becomes grounded, someone must walk around the entire fence in search of what is causing the problem.  We wanted to minimized the area that person has to search.  Initially we hoped to be able to use some sort of algorithm that would determine exactly where in the fence to problem was occurring.  Upon further research, that was deemed very difficult and perhaps impossible given our budget.  If we could not be exact, we could at least reduce the search area.  By placing four measuring stations at equal intervals along the fence it will be possible to narrow down which fourth of the fence the problem is occurring at, saving time and energy.
	Another innovation that our project hopes to accomplish is the power source.  Early ideas were about drawing power from the electric fence itself, however it was not feasible for this project because when the fence becomes grounded, the electronics would lose their power supply.  We talked to Tim May and he suggested using solar panels connected to a battery.  It would be very convenient and eco-friendly to have a sustainable energy source.  Once we have much of our electronics assembled we will use a multi-meter to determine the size of solar panels and battery that will be used. 
	A very innovative idea that we had was to send notifications to Andre when his fence became grounded.  We struggle first thought to use an Arduino shield that would connect to the internet to send messages to Andre’s phone.  We came to the revelation that that is not thinking globally and even in Andre’s case there is probably no Wi-Fi connection at the actually location of the electric fence.  We then took into consideration using a GMS shield, however that would require obtaining a network connection, most likely with cell phone company.  That was determined to be impractical because it would require a constant financial cost.  Our focus thus turned towards wiring a prepaid cell phone to an Arduino to send messages.  That was not the best option for similar financial reasons, but might be more practical.  However through more research we found a much better option.  It is called an XBee.  It is used to communicate with multiple Arduino’s. It is relatively inexpensive and there are a wide variety to choose from to get exactly what will be needed.  Our idea is to use XBees to communicate to an Arduino located in or around Andre’s house that will either display a message about the status of the electric fence or will use Wi-Fi from the house to send a message to Andre’s phone. 
 
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
