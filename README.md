# qcp-iot

QCP for IoT — 超低延迟、高保证的 UDP 可靠传输。

基于 QCP TLB 语义交付，专为传感器遥测、设备控制、OTA 等 IoT 场景设计。

| 数据类型 | QCP 通道 | 说明 |
|----------|----------|------|
| 传感器读数 | REALTIME | 最新值覆盖，零恢复延迟 |
| 控制指令 | CRITICAL | deadline 内有界可靠 |
| OTA / 配置 | BATCH | 强可靠 ARQ |

## Supported Platforms

- ESP32 / ESP8266
- Raspberry Pi
- STM32
- Nordic nRF

## Usage (ESP32)

```cpp
#include <qcp_iot.h>

QcpClient client;
client.connect("192.168.1.100", 9000);

// 遥测 — REALTIME
client.sendRealtime(sensorData);

// 控制指令 — CRITICAL, 8ms deadline
client.sendCritical(command, 8);
```

## Features

- Ultra-low latency telemetry (REALTIME)
- Reliable command delivery (CRITICAL)
- OTA firmware update (BATCH)
- Minimal CPU / memory footprint

## License

MIT License
