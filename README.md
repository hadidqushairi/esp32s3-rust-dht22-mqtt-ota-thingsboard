# esp32s3-rust-dht22-mqtt-ota-thingsboard
ESP32-S3 + Rust project reading DHT22 and sending telemetry to ThingsBoard via MQTT with millisecond timestamps. Includes Wi-Fi setup, MQTT auth/clientId, and OTA over MQTT. Ships with 8MB partition table (factory, ota_0, ota_1). Build/flash with the esp toolchain and espflash.

first step: Installation
## Hardware
- ESP32-S3
- DHT22 on GPIO4

## Build environment

```bash
sudo apt update
sudo apt install -y git curl build-essential pkg-config libssl-dev libudev-dev clang lld
cargo install espup
espup install
source ~/export-esp.sh
cargo install cargo-generate espflash
