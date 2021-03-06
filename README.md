# flightcomputer2020
This repo contains EAGLE and other design files for PCBs in the 2020-2021 flight campaign.  


## Project Stages
### 1.  October Skies Flight Computer
This is the stage we are currently at. For the October Skies event, we test our new avionics / recovery / airframe platforms on a smaller model rocket. This year we are building our platform around the Raspberry Pi 4B, and are trying to figure out the best way of simplifying the interface between the Raspberry Pi and the other sensors( Pi included). The problems to address are how to power everything and transmit data to the Pi, while keeping things simple and easy to assemble. The approach we chose was to make this as a Pi Hat, with designated ports for power and data for each separate component. This way, final rocket assembly can be plug-and-play for the avionics bay, with no hands on working required other than plugging things into their corresponding port. For now, the october skies computer will be done as a proto-board for the radio and power distribution, and a separate system for the RRC3 (used to deploy the parachutes). The diagram below fully illustrates how the flight computer will be set up for the october skies launch.

![Flight Computer Diagram](/Documentation/FlightComputerDiagram.PNG)
### 2.  Final Flight Computer
This area will be populated after the October skies launch, as we build out the plan for the final flight computer. What is likely to come, is that we join the separate RRC3 power system and data, and connect it to the Pi Hat also.

## How to Use
We're going to be learning how to best use this repo together, but for now, here are some best practices:
1. If you need access to this folder, please reach out to either Magdalena or Sebastien on Slack or Discord (links will not be posted here).
2. Create your own folder under your name under the flightcomputer2020 folder.  For now, we're going to push and pull everything straight from the master branch, and when we start comparing, reviewing, and blending our designs, we'll start different branches.
3. Make sure you save all the files generated by whichever CAD software you're using and push them to your folder.


## Datasheets / Parts Info
(Datasheets will be listed where available, otherwise site links to the company or product)
1.  Recovery System // RRC3 //[Documentation (PDF Download)](https://www.missileworks.com/app/download/965482691/RRC3+User+Manual+v1.60.pdf)
2.  Main Computer // Raspberry Pi 4B //[Documentation](https://www.raspberrypi.org/documentation/hardware/raspberrypi/README.md)
3.  Navigation Sensor // SBG Ellipse 2 - N //[Site Link](https://www.sbg-systems.com/products/ellipse-series/)
4.  Radio // RFD900 // [Documentation](https://files.rfdesign.com.au/Files/documents/RFD900%20DataSheet.pdf)  // 

## Extra Resources
1. Link to the [student version of EAGLE](https://www.autodesk.com/education/edu-software/overview?sorting=featured&page=1) (you need to use your student email)
2. Link to [Fritzing](https://www.filehorse.com/download-fritzing-64/download/) for protoboard design
3. Best site for BUYING components: [Mouser.ca](https://www.mouser.ca/)
4. Best site for LIBRARY FILES For components: [Digikey.ca](https://www.digikey.ca/)
5. Good [Git cheat sheet](https://education.github.com/git-cheat-sheet-education.pdf) to print and have by your desk
5. Inspiration for our final flight computer from the [MIT Pyxida](http://rocketry.mit.edu/2016/09/pyxida-flight-computer/) 

## Decision Log
In reverse chronological order

##### Sep. 26, 2020
Big take-aways for the day:  Welcomed new member to hardware and discussed the power regulation that we'll need to start thinking about for our January mini-launch.
1. Step down ~7V to 5V exactly 
2. Brownout protection on Pi - some kind of capacitance that will keep up ~2A over ~1s (maybe more with margin of error)
3. Current limiting to RRC3 so we don't get the full ~400A output.
4. Include a power switch (can we have backup and main on same battery? Is that even a good idea?)


##### Sep. 19, 2020
Big take-aways for the day:
1. Using 9V on RRC3 --> Remove need for brownout protection, current limiting.
2. Making a pi-hat from a protoboard to fit on top of Pi (most preferable if height does not exceed USB jacks)
3. Still need a switch
4. Still need a voltage converter
5. Still need rails from batteries into pi-hat.
6. Keep using Github
7. Download/ use Fritzring for visualizing final pi hat
8. Update markdown file to include all of this.
