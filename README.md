
# TinyNTPClient

A minimal, header-only Network Time Protocol (NTP) client for Arduino and compatible platforms, designed for efficiency and portability. Works with any UDP API (e.g., WiFiUDP, EthernetUDP).

[![Arduino Library](https://img.shields.io/badge/Arduino-Library-blue.svg)](https://www.arduino.cc/reference/en/libraries/)
[![License: GPL v3](https://img.shields.io/badge/License-GPLv3-blue.svg)](https://www.gnu.org/licenses/gpl-3.0)

## Features

- Retrieves accurate UTC time from NTP servers
- Minimal resource usage, suitable for embedded/IoT
- Header-only, easy to integrate
- Supports timezone offset
- Works with any UDP API (WiFiUDP, EthernetUDP, etc.)
- Returns time as seconds, milliseconds, or `std::tm` struct
- cmake support

## Installation

1. Copy `TinyNTPClient.h` to your Arduino `libraries` folder or your project.
2. Include the header in your sketch.

## Usage

```cpp
#include <WiFiUdp.h>
#include "TinyNTPClient.h"

WiFiUDP udp;
TinyNTPClient<WiFiUDP> ntp(udp);

void setup() {
	// Connect to WiFi here...
	ntp.begin();
}

void loop() {
	if (ntp.update()) {
		uint32_t now = ntp.getTimeSec();
		Serial.print("UTC Time: ");
		Serial.println(now);
	}
	delay(60000); // Update every minute
}
```

## API

- `begin()`: Initialize and sync time.
- `end()`: Reset client state.
- `update()`: Query NTP server and update time.
- `getTimeSec()`: Get current time in seconds (UTC).
- `getTimeMs()`: Get current time in milliseconds (UTC).
- `getTm()`: Get current time as `std::tm` (UTC).
- `setTimeOffsetSeconds(offset)`: Set timezone offset in seconds.
- `setTimeOffsetHours(hours)`: Set timezone offset in hours.
- `setServer(server, port)`: Set NTP server and port.

## Timezone Handling

NTP always returns UTC. Use `setTimeOffsetHours()` or `setTimeOffsetSeconds()` to adjust for your local timezone.

## License

This library is licensed under the GNU GPL v3. See `License.txt` for details.

## Author

- Maintainer: <phil.schatzmann@gmail.com>
- [GitHub Repository](https://github.com/pschatzmann/TinyNTPClient.git)

