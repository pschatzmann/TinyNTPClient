# TinyNTPClient

[![Arduino Library](https://img.shields.io/badge/Arduino-Library-blue.svg)](https://www.arduino.cc/reference/en/libraries/)
[![License: GPL v3](https://img.shields.io/badge/License-GPLv3-blue.svg)](https://www.gnu.org/licenses/gpl-3.0)

A minimal, header-only Network Time Protocol (NTP) client for Arduino and compatible platforms, designed for efficiency and portability. It works with any Arduino UDP API (e.g., WiFiUDP, EthernetUDP).


## Features

- Retrieves accurate UTC time from NTP servers
- Minimal resource usage, suitable for embedded/IoT
- Header-only, easy to integrate
- Supports timezone offset
- Works with any UDP API (WiFiUDP, EthernetUDP, etc.)
- Returns time as seconds, milliseconds, or `std::tm` struct
- cmake support

## Installation in Arduino

You can download the library as zip and call include Library -> zip library. Or you can git clone this project into the Arduino libraries folder e.g. with

```
cd  ~/Documents/Arduino/libraries
git clone https://github.com/pschatzmann/TinyNTPClient.git
```

I recommend to use git because you can easily update to the latest version just by executing the git pull command in the project folder. 


## Documentaion

- [TinyNTPClient](https://pschatzmann.github.io/TinyNTPClient/html/class_tiny_n_t_p_client.html) class
- [Example Sketch](https://github.com/pschatzmann/TinyNTPClient/blob/main/examples/ntp-wifi/ntp-wifi.ino)


## License

This library is licensed under the GNU GPL v3. See `License.txt` for details.


