# Sensor Calibration
## IAQ Mode vs SEL Mode
The BME690 has two modes of operation IAQ and SEL and calibration is approached differently for each mode. 
### IAQ
In IAQ mode we choose a 4 day (quicker to register change) or 28 day (slower to reflect change) calibration period. During this time the sensor will learn the environment and calibrate itself. When we choose to subscribe to TVOC the adaption algorithm changes again, and controlling the heat build up from the hot-plate is important to achieve accurate environmental readings (temp, humidity). Also a new sensor has to be burned in for 24 hours before it can be used for accurate readings.

### SEL
SEL mode is very different and calibration is internal to the sensor and BSEC3 software, fine-tuning the parameters stored in the sensor registers. The easiest access to this is by saving and loading state, which will speed up the process of calibration.  

## Saving and Loading State
When first starting a BME690 in SEL mode (sniffing mode) it will take a long time to get accurate readings, approximately 20 minutes. During this start up time a single sensor in SEL mode may seem to stick on a class (100% wrong) which is not accurate to the environment it is in, and it is immune to changes. After the calibration period the sensor will become more responsive to changes (still taking up to 5 min to report changes) and the readings will be more accurate.

So far I have just used these empirical values to implement state saving and loading. See sniff-state.py in the tools directory of [bme69x-python-library-bsec3.3.0.0](https://github.com/mcalisterkm/bme69x-python-library-bsec3.3.0.0). In my testing this reduces the calibration time down to 5 - 10 min.

## To-Do
In the future I plan to see how effective tracking BSEC_OUTPUT_RUN_IN_STATUS or BSEC_OUTPUT_STABILIZATION_STATUS might be in SEL mode to replace the empirical timing. . 
