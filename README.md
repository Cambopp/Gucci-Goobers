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
The first step in the project was measuring current/ or voltage to tell if the fence is down.  The options in order to accomplish this where as follows:
- Standard voltmeter or multimeter
- Specialized voltmeter for an electric fence
- Non-invasive current sensor(5 Amps maximum)
  
The  option of a standard voltmeter or multimeter where ruled out early on because the quick pulses of an electric fence would damage these. In addition, a specialized voltmeter costs upward of 70$ and was not within budget because of our goal to have four stations. The non-invasive current senor was a much cheaper option (10$) and would not get damaged, so it was the best option. Specifically a a Amp maximum on the current sensor would yield accurate enough readings.

When a fence becomes grounded, someone must walk around the entire fence in search of what is causing the problem. We wanted to minimized the area that person has to search by either using an algorithm or multiple ensors. The idea of deriving an algorithm that could tell where the grounding issue occured between two sensors was deemed something that could not be done in the instance of a grounded electric fence. However, putting four sensors along the fence would allow us to determine beetween what two sensors the grounding occured at. That way only one fourth of the fence would need to be searched for problems.

The Goals for powering the project were that it be reliable and self sufficient. One idea was to draw power from the electric fence itself, however it was not feasible for this project because when the fence becomes grounded, the electronics would lose their power supply. On the other side of the coin, solar panels would be environentaly friendly but could be unreliable at night and on cloudy days. Having a solar panel charge a battery would make a much more reliable power source because there would be extra charge for cloudy times and night, but would also not have batteries that would need replacement.

Finally, there was the goal that notifications be send to the owner of the fence. Here were the different alternatives that were suggested:
  - Wi-Fi shield
  - GMS shield
  - Xbee

The cons of using a Wi-Fi shield were that using Wi-Fi is not thinking globally because farms do not typically have Wi-Fi. Even in Andre’s case there is no Wi-Fi connection at the actual location of the electric fence. A GMS shield would work well, but it would require obtaining a network connection, which is not within our budget and would require continued payments. XBee's were the final idea. They can communicate between multiple arduinos and cheeper XBee's can communicate 300 feet, which would work well for what we need. Additionaly, XBee's are easy to use with Arduinos.

##Testing & Anaylsis
- Critical Parts & Analysis

The critical part of our whole design, on which we presented, was determined to be the XBee modules working with the Arduinos and communicating with each other.  As such, we had to make sure that our code was correct and that our XBees could in fact talk to each other effectively.  This proved a success, and our presentation ultimately went well.  Under analysis, our Arduino seems to be reading currents correctly, even after soldering its components to the prototyping board. The XBees are communicating correctly and are outputting readings that make sense.  
- Testing

The last time we had a chance to test our current sensor in the real world was without the XBees, so we're still not sure how they will fare on an actual electric fence.  However, when we did test our current sensor on that fence, its readings were very reliable (and not distorted from the ambient electromagnetic fields in the ITLL).  We're very happy with this, and hope that the new code that we are in the process of writing can be used in our final design.

##Bill Of Materials
  - Fence measuring unit($80)
    - Arduino($17.50)
    - Xbee($20)
    - Weather Proof Case($13)
    - Audio Jack($4.50)
    - Xbee Shield and Stackable Headers($15)
    - Current Sensor($10)
  - Home Unit($52.50)
    - Arduino($17.50)
    - Xbee($20)
    - Xbee Shield and Stackable Headers($15)
  - Copper Wire and Battery for testing($8)
  - Future (~$130)
    - Solar Powee(~$30)
    - Wi-Fi Shield(~$40)
    - Poster($60)
  
##Final Design
- Description: Our final design has to be able to detect when the client's electric fence is down and relay this information to the client. Additionally it has to be powered consistently, and endure exposure to weather. It consists of the following components which allow it to meet these requirements.
  - Non invaisve current sensor: This is arguably the most important part of the design. It allows the device to detect when there is no current in the fence. A non invasive current sensor uses the magnetic fields created by the current moving through the wire in order to infer the current that is passing through it. This method of obtaining the current is important to the project, as a simple ammeter could easily be damaged by the high voltage that passes through an electric fence. The non invasive current sensor doesn't need to be in contact with the fence to pick up a current meaning it won't be damaged. 
  - Arduino RedBoard: The RedBoard processes the information received by the current sensor in order to allow us to decide when to send messages to the client. It will send a message whenever the current picked up by the current sensor hits 0 a certain number of times in a specific time frame. This will prevent messages from being sent every time the sensor randomly picks up a 0. 
  - Xbees/GSM Shield: This component is what allows the device to communicate with the client. We currently have two plans for how to accomplish this. The first is the ideal plan, which is to use the GSM shield. This will allow the device to send a text message to the client when the fence is down. This is ideal as the client can be anywhere and as long as they have their phone, they will receive the message immediately. It's drawbacks are caused by time constraints and potential financial constraints. If it turns out we don't have the time or money to implement this component, we will instead use Xbees. Xbees allow for two arduinos to communicate with each other. Using these we could have the device communicate with a seperate arduino located somewhere more accessable to the client. This seperate arduino would be fitted with an LED light which lights up when the fence is down. This is less ideal as it is more work for the client to make sure to check it, however it easily fits into our budget and timeline therefore if the first plan fails this is a solid backup. 
  - Pelican weatherproof case: This allows the device to withstand any weather conditions. It houses the Redboard, the XBee and the batteries.
  - Solar Panel + Rechargeable Batteries: This component is for powering the device. With the solar panel, the device is able to draw power without having to be plugged in. This is important as the electric fence is located outside, and there was a possibility of another power supply not being available. The rechargeable batteries allow the power supply to be consistent. The solar panel charges the batteries which supply the device. This means that even at night, or during the rain, the device should still receive power. 
- Manufacturing Process: This project was not very manufacturing heavy, however there were a few things that needed to be built. The first part was getting the sensor hooked up to the redboard. This simply involved building the circuit for it, and getting a connecting piece to allow us to attach the sensor to the bread board. the next step involved attaching the xbees. In order to do this we required an xbee shield with stackable headers, which would be soldered to the shield then plugged in to the redboard. Following this the circuit on the breadboard needed to be soldered to the shield. The same needed to be done for the shield and redboard containing the receiving xbee and the LEDs. The next step involves the power supply. The batteries need to be hooked up and plugged in to the redboard, as well as the solar panel to charge them. Finally the portion of the device that is on the electric fence needs to be placed in the weatherproof case. First a hole needed to be drilled in the case in order for the wires connecting the solar panel and the sensor to reach inside, then the redboard and batteries needed to be placed inside, and the hole sealed. 

>>>>>>> origin/master
