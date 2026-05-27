## Cleaning Sensors

The shuttle board sensors and sensor modules are easily contaminated by dust, dirt, and fingers as the board is handled. Unless you wear gloves and work in a clean-room environment, you will need to clean the sensors. 

Why? Because contamination on the BME690 metal case, will gas out as the heater plate in the BME690 goes to work, and this will cause interference with the sensors readings. 

The next question is when should you clean the sensors? And often it is clear that contamination has occured, based on the results you are recording. In the figure below sensor U5 is contaminated and predicting the wrong class while all the rest are correctly predicting the class. Look for sensors that are slow to respond to change, as this can be a sign of contamination as well.

![smear-sensor.png](img/smear-sensor.png)

I used a lint-free pad with no product on it, and gently wiped the 8 x BME690 metal sensor cans.  Initially it looked successful, but clearly I picked some contamination and wiped it across both U5 and U6. A new pad and a more careful wipe of U5 and U6 was needed to get the sensors clean again.

Should I use distilled water or isopropyl alcohol? I have read a Honeywell document that suggests using distilled water to damp a lint free cloth. I have also used isopropyl alcohol to clean sensors, but only with everything powered off and being carful not to get any liquid into the sensor module. I have a small brush that is designed for use on circuit boards, which is very useful for removing dust and dirt in small places.

if you do use a liquid, make sure to let the sensor dry completely before powering it back on. And take the usual anti-static precautions when working with the sensors.

Whatever you do, you do it at your own risk. These sensors are delicate and can be damaged by liquids, and over saturating with cleaning products can ruin a sensor.

