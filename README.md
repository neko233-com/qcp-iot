# qcp-iot

QCP integration for IoT devices.

## Supported Platforms

- ESP32/ESP8266
- Raspberry Pi
- Arduino (with Ethernet/WiFi shield)
- STM32
- Nordic nRF

## Usage

### ESP32

```cpp
#include <qcp_iot.h>

void setup() {
    WiFi.begin(ssid, password);
    while (WiFi.status() != WL_CONNECTED) {
        delay(1000);
    }
    
    QcpClient client;
    client.connect("192.168.1.100", 9000);
    
    client.send("hello");
    
    uint8_t buffer[256];
    int n = client.receive(buffer, sizeof(buffer));
}

void loop() {
    // Handle QCP traffic
}
```

## Features

- Low memory footprint (< 10KB RAM)
- Minimal CPU usage
- Power efficient
- MQTT compatible

## License

MIT License
