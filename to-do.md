Resources:
Signalk data format:
https://github.com/SignalK/specification/blob/master/gitbook-docs/data_model.md
https://github.com/SignalK/specification/blob/master/gitbook-docs/keys.md

Arduino examples:
https://github.com/emilecantin/arduino-signalk/blob/master/arduino_sketch/Sensors/Sensors.ino



‘fully  charged’  when the following ‘charged parameters’  are met:  the  voltage  exceeds  13.2V  and simultaneously  the (tail-)  charge current  is  less  than  4.0%  of  the total battery  capacity  (e.g.  8A  for  a 200Ah battery)  during 3  minutes. 

A battery is considered non-usable if its nominal capacity falls below 60 to 80%.
End of life factor used is 1.25 for battery sizing.


temperature compensated fuel gauging?

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
