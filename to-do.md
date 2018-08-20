Resources:
Signalk data format:
https://github.com/SignalK/specification/blob/master/gitbook-docs/data_model.md
https://github.com/SignalK/specification/blob/master/gitbook-docs/keys.md

Arduino examples:
https://github.com/emilecantin/arduino-signalk/blob/master/arduino_sketch/Sensors/Sensors.ino



‘fully  charged’  when the following ‘charged parameters’  are met:  the  voltage  exceeds  13.2V  and simultaneously  the (tail-)  charge current  is  less  than  4.0%  of  the total battery  capacity  (e.g.  8A  for  a 200Ah battery)  during 3  minutes. 

A battery is considered non-usable if its nominal capacity falls below 60 to 80%.
End of life factor used is 1.25 for battery sizing.
electrical.batteries.*.capacity.stateOfHealth
State of Health, 1 = 100%
**Units:**ratio


temperature and peukert compensated fuel gauging?


vetus sealed maintenance free (SMF) with magic eye 
From vetus AGM:
The  battery  is  fully  discharged  when  the  volt
age  drops  to  10.5  Volts  (or  21.0  Volts)  for  the 
nominal discharge current.
13.8V (trickle charging). 
As  a  rule,  a charge  factor  of  1.15  should  be  maintained
This means that you should charge 1.15 times the  Ah  that  was  taken  from  the  previous  battery discharge. 
When  charging,  the  VETUS  battery  may  not become  hotter  than  52°C.  The  charging  voltage  may  not  be  greater  than  14.8V,  and  this not for longer than 5 hours, 
During   charging,   the   clamp   voltage   will 
increase  from  over  2  Volts  to  about  2.7  Volts 
per  cell,  depending  on  the  charging  system 
used.

When a voltage of 2.4 Volts per cell is reached, the battery generates gas (hydrogen and oxygen).  The  battery  is  then  75  to  80%  charged. During   this   gas   development   phase,   the charge current should not exceed 8 Amps per 100 Ah.

config.json:

{
  "enabled": true,
  "id": "BATMON",
  "pipeElements": [
    {
      "options": {
        "baudrate": 38400,
        "device": "/dev/ttyUSB0"
      },
      "type": "providers/serialport"
    },
    {
      "type": "providers/from_json"
    }
  ]
}
