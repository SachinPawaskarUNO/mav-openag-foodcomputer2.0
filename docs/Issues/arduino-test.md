# Unable to Display Sensor Readings on UI

:house: [Back to Trouble Shooting](https://github.com/SachinPawaskarUNO/mav-openag-foodcomputer2.0/blob/master/docs/IssueTroubleShooting.md)

We were facing the issue of not able to detect the Arduino port, when connected to the Raspberry PI3. We tried changing the port to S0 assuming it is an issue with the serial port Acm0. We were still seeing an error message stating "Serial Port Acm0 not found" in spite of changing the serial port to S0. We later realized that it is an issue with the Arduino Mega 2560 that is connected to the raspberry pi. This issue was sorted after replacing the arduino and we were able to flash the new Arduino in the first attempt.

The command used to check the ports on the PI-
> ls -l /dev
