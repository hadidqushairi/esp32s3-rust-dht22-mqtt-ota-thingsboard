# esp32s3-rust-dht22-mqtt-ota-thingsboard
ESP32-S3 + Rust project reading DHT22 and sending telemetry to ThingsBoard via MQTT with millisecond timestamps. Includes Wi-Fi setup, MQTT auth/clientId, and OTA over MQTT. Ships with 8MB partition table (factory, ota_0, ota_1). Build/flash with the esp toolchain and espflash.
first step: Installation
1) Prerequisites (Ubuntu)
sudo apt update
sudo apt install -y git curl build-essential pkg-config libssl-dev libudev-dev clang lld

2) Install ESP Rust toolchain  flasher
cargo install espup
espup install

Load toolchain env each new terminal:
source ~/export-esp.sh

Serial permission (optional):
sudo usermod -aG dialout $USER  {logout/login after}

3) Project tools
cargo install cargo-generate espflash

4) Create project from template
cargo generate esp-rs/esp-idf-template cargo
When prompted:
- Project Name: project-iot
- Chip: ESP32-S3
- Advanced template options: false
cd project-iot

5) Add your code
Replace Cargo.toml and src/main.rs with your versions (DHT22, Wi-Fi, MQTT, OTA). Save files.

6) Build
source ~/export-esp.sh
cargo build
(Release) cargo build --release

Ensure IDF PATH is empty
echo $IDF_PATH
If not empty: unset IDF_PATH
