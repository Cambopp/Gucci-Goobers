The Gucci Goobers
=============

This is the repository for the Gucci Goobers, a group of freshman engineers at CU Boulder.
Images that accompany the design report can be found on the wiki page.

#Design Report

##Background/Client Info:
  For the Gucci Goobers’ final project, we will be working with Andre Houssney from Jacob Springs Farm. A number of problems, or inconveniences, were posed at the farm, such as ensuring the chicken coop is closed at night, measuring the remaining water supply of the farm and cuing the ventilation of the greenhouse, among other things. We decided on working with the electric fence, which contains the livestock. The problem with the electric fence is that it can be taken down very easily through vegetation coming in contact with the fence and grounding the current, or animals breaking the fence. Many of the animals are very obedient, and once they’re shocked once they will not go near the fence again. However, some animals (such as the goats and sheep) are more persistent, and will test the fence regularly. If there is no shock emitted by the fence, the goats and sheep can escape. The goal of our project is to create a device which notifies our client when the fence is down. We would like to be able to detect where the problem is in relation to a fixed point. This would save the client a great deal of time. Without detecting the location of the shortage, they must walk the entire perimeter of the fence. This is not ideal as we are aiming to save the client as much time as possible. We believe this could benefit livestock farmers at an international level; saving them time and money, and, in turn, allowing them to be more productive.


##Design Requirements:
- The sensor must be able to 
  - Withstand a voltage of 12000 V.
  - Measure a currents ranging between 0 and 5 Amps of pulsing current.
- The Device must be able to
  - Transmit signal from one corner of the fence to another, and also to the “mother” Arduino. Corners can be between 100 and 2000 feet apart depending on the configuration of the fence.
  - Determine the location of short.
  - Withstand wind, rain, heat, snow and frost.
- The power source must be able to supply 5 volts to power the Arduino.
- The Arduino must be able to send an sms to the clients phone at least once a day and still remain under the budget.
- The production cost must be under 375 Dollars.



##Design Alternatives/Brainstorming
- Measuring current/voltage
  - Standard voltmeter or multimeter: The quick pulses of an electric fence would damage these.
  - Specialized voltmeter for an electric fence: This was upward of 70$ and not within budget since our project requires four of them.
  - Non-invasive current sensor(5 Amps maximum): This would be unlikely to be damaged because it does not directly touch the fence and having a sensor that works with low current would give a more accurate reading compare to sensor that read up to 30 Amphere.
- Minimizing search area: When a fence becomes grounded, someone must walk around the entire fence in search of what is causing the problem. We wanted to minimized the area that person has to search.
  - Algorithm: An idea was to derived an algorithm that could tell where the grounding issue occured between two sensors.
  - Four sensors: Putting four sensors along the fence would allow us to determine beetween what two sensors the grounding occured at. That way only one fourth of the fence needs to be searched for problems.
- Power source
  - Electric fence: Early ideas were about drawing power from the electric fence itself, however it was not feasible for this project because when the fence becomes grounded, the electronics would lose their power supply.
  - Solar panel: Solar panels would be environentaly friendly but could be unreliable at night and on cloudy days.
  - Solar panel and battery: Having a solar panel charge a battery would make a much more reliable power source.
- Sending notifications
  - Wi-Fi shield: We came to the revelation that using Wi-Fi is not thinking globally because farms to not typically have Wi-Fi. Even in Andre’s case there is no Wi-Fi connection at the actual location of the electric fence.
  - GMS shield: That would require obtaining a network connection, which is not within our budget
  - Xbee: Can communicate between multiple arduinos and cheeper ones can communicate 300 feet, which would work well for what we need.
  

##Testing & Anaylsis
- Critical Parts & Analysis

The critical part of our whole design, on which we presented, was determined to be the XBee modules working with the Arduinos and communicating with each other.  As such, we had to make sure that our code was correct and that our XBees could in fact talk to each other effectively.  This proved a success, and our presentation ultimately went well.  Under analysis, our Arduino seems to be reading currents correctly, even after soldering its components to the prototyping board. The XBees are communicating correctly and are outputting readings that make sense.  
- Testing

The last time we had a chance to test our current sensor in the real world was without the XBees, so we're still not sure how they will fare on an actual electric fence.  However, when we did test our current sensor on that fence, its readings were very reliable (and not distorted from the ambient electromagnetic fields in the ITLL).  We're very happy with this, and hope that the new code that we are in the process of writing can be used in our final design.


>>>>>>> origin/master
