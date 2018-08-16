Resources:
Signalk data format:
https://github.com/SignalK/specification/blob/master/gitbook-docs/data_model.md
https://github.com/SignalK/specification/blob/master/gitbook-docs/keys.md

Arduino examples:
https://github.com/emilecantin/arduino-signalk/blob/master/arduino_sketch/Sensors/Sensors.ino


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
