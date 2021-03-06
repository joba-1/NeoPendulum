# NeoPendulum
Simulates a thread pendulum with a neopixel RGB strip

## Required Hardware
* Runs on an ESP8266 (e.g. a NodeMCU) with a NeoPixel compatible RGB strip (the more pixels the better...)
* Needs two digital pins (or rather just one, the other is for the internal led to see the wlan connection status)
* Build your firmware with PlatformIO (adapt platformio.ini to match your upload config) or Arduino IDE
* You will need libraries ArduinoJson and Adafruit_Neopixel installed

## Optional WLAN
It does not need WLAN access to display the pendulum, but it is still nice to have:
* Replace SSID and PASS (or WlanConfig.h) with your own WLAN settings
* It will use DHCP to get an IP address and show up on your network as `http://NeoPendulum.local`
* Call it with curl/wget or a web browser to configure the device with its internal webserver - but no fancy gui, sorry :)
* You can set the maximum angle, the thread length and the local gravitational acceleration
* Of course you can set colors for the pendulum mass, the acceleration vector and the background
* Parameters are changed permanently in EEPROM/Flash until you erase them with `http://NeoPendulum.local/clear`
* You can even update its firmware with a simple curl -vF 'image=@firmware.bin' NeoPendulum.local/update

Have fun!
