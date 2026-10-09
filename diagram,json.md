{
  "version": 1,
  "author": "OLED Automotive ECU",
  "editor": "wokwi",
  "parts": [
    {
      "type": "board-st-nucleo-c031c6",
      "id": "nucleo",
      "top": 29.63,
      "left": -327.38,
      "attrs": {}
    },
    {
      "type": "wokwi-pushbutton",
      "id": "btn_ign",
      "top": -128.2,
      "left": 67.2,
      "attrs": { "color": "green", "label": "Ignition" }
    },
    {
      "type": "wokwi-pushbutton",
      "id": "btn_fault",
      "top": -128.2,
      "left": 182.4,
      "attrs": { "color": "red", "label": "Inject Fault" }
    },
    {
      "type": "wokwi-potentiometer",
      "id": "pot_volt",
      "top": 27.5,
      "left": 153.4,
      "attrs": { "label": "RPM" }
    },
    {
      "type": "wokwi-potentiometer",
      "id": "pot_temp",
      "top": 27.5,
      "left": 268.6,
      "attrs": { "label": "Temp" }
    },
    {
      "type": "wokwi-potentiometer",
      "id": "pot_rpm",
      "top": 27.5,
      "left": 374.2,
      "attrs": { "label": "Battery" }
    },
    {
      "type": "wokwi-led",
      "id": "led_status",
      "top": 34.8,
      "left": 599,
      "attrs": { "color": "green", "label": "Engine On" }
    },
    {
      "type": "wokwi-led",
      "id": "led_fan",
      "top": 34.8,
      "left": 483.8,
      "attrs": { "color": "blue", "label": "Cooling Fan" }
    },
    {
      "type": "wokwi-led",
      "id": "led_warn",
      "top": 34.8,
      "left": 541.4,
      "attrs": { "color": "red", "label": "Warning" }
    },
    {
      "type": "wokwi-lcd1602",
      "id": "lcd1",
      "top": -320,
      "left": -196,
      "attrs": { "pins": "i2c" }
    },
    {
      "type": "wokwi-buzzer",
      "id": "bz1",
      "top": -141.6,
      "left": 433.8,
      "attrs": { "volume": "0.1" }
    }
  ],
  "connections": [
    [ "nucleo:GND", "btn_ign:1.l", "", [] ],
    [ "nucleo:D2", "btn_ign:2.l", "", [] ],
    [ "nucleo:GND", "btn_fault:1.l", "", [] ],
    [ "nucleo:5V", "pot_rpm:VCC", "red", [] ],
    [ "nucleo:GND", "pot_rpm:GND", "black", [] ],
    [ "nucleo:5V", "pot_temp:VCC", "red", [] ],
    [ "nucleo:GND", "pot_temp:GND", "black", [] ],
    [ "nucleo:5V", "pot_volt:VCC", "red", [] ],
    [ "nucleo:GND", "pot_volt:GND", "black", [] ],
    [ "nucleo:GND", "led_status:C", "black", [] ],
    [ "nucleo:GND", "led_fan:C", "black", [] ],
    [ "nucleo:GND", "led_warn:C", "black", [] ],
    [ "nucleo:5V.2", "pot_rpm:VCC", "red", [ "h0" ] ],
    [ "nucleo:5V.2", "pot_temp:VCC", "red", [ "h0" ] ],
    [ "nucleo:5V.2", "pot_volt:VCC", "red", [ "h0" ] ],
    [ "nucleo:GND.3", "pot_rpm:GND", "black", [ "h0" ] ],
    [ "nucleo:GND.3", "pot_temp:GND", "black", [ "h0" ] ],
    [ "nucleo:GND.3", "pot_volt:GND", "black", [ "h0" ] ],
    [ "nucleo:D2", "btn_ign:2.r", "white", [ "h0" ] ],
    [ "nucleo:D3", "btn_fault:2.r", "purple", [ "h160.85", "v-336", "h163.2" ] ],
    [ "nucleo:GND.4", "led_status:C", "black", [ "h0", "v124.8", "h825.6" ] ],
    [ "nucleo:GND.4", "led_warn:C", "black", [ "h0", "v124.8", "h864" ] ],
    [ "nucleo:GND.4", "led_fan:C", "black", [ "h0", "v124.8", "h777.6" ] ],
    [ "nucleo:D4", "led_status:A", "limegreen", [ "h0" ] ],
    [ "led_fan:A", "nucleo:D5", "blue", [ "v0" ] ],
    [ "nucleo:D6", "led_warn:A", "cyan", [ "h0" ] ],
    [ "nucleo:5V.1", "lcd1:VCC", "red", [ "h-57.6", "v-480" ] ],
    [ "lcd1:GND", "nucleo:GND.2", "black", [ "h-105.6", "v460.8" ] ],
    [ "nucleo:D15", "lcd1:SCL", "green", [ "v0", "h64.85", "v-268.8", "h-249.6", "v-115.2" ] ],
    [ "lcd1:SDA", "nucleo:D14", "yellow", [ "h-19.2", "v115.4", "h249.6", "v297.6" ] ],
    [ "pot_rpm:SIG", "nucleo:A2", "yellow", [ "v0" ] ],
    [ "pot_temp:SIG", "nucleo:A1", "magenta", [ "v0" ] ],
    [ "pot_volt:SIG", "nucleo:A0", "gray", [ "v0" ] ],
    [ "nucleo:GND.5", "btn_ign:1.l", "black", [ "h0" ] ],
    [ "nucleo:GND.6", "btn_fault:1.l", "black", [ "h394.05", "v-307.2", "h76.8" ] ],
    [ "nucleo:GND.9", "bz1:1", "black", [ "h0" ] ],
    [ "bz1:2", "nucleo:D7", "green", [ "v0" ] ]
  ],
  "dependencies": {}
}
