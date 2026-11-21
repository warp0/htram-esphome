# HTRAM Release v2.4.2

## Огляд релізу (Release Overview)
Реліз `v2.4.2` об'єднує в один стабільний випуск пакет room-dashboard/OTA змін, міграцію клієнта повітряних тривог на сервісний API JAAM (`/data_service_v1`) та оновлені статус-іконки dashboard (блискавка для живлення і мигалка для стану JAAM).

## Основні зміни (Key Features & Improvements)

### 1. Міграція на сервісний WebSocket API JAAM (`/data_service_v1`)
- Клієнт `jaam_ws` працює через `ws://ws.jaam.net.ua:80/data_service_v1`.
- Додано/оновлено ідентифікацію сервісу (`service_id`, `service_name`, `website`, `contact`, `version`) і `hello:<JSON>`.
- Покращено обробку reconnect/backoff і сервісних кодів закриття.
- Виправлено обробку жовтого рівня тривоги при одночасному legacy-біті.

### 2. Room Dashboard + room-aware OTA
- Пакет room-dashboard змін для кімнатних профілів (`living`, `bedroom`, `office`, `kids-1`, `kids-2`) і відповідних OTA-бінарників.
- CI-релізний пайплайн публікує room-артефакти разом із `htram-standalone.bin`, `gd32_firmware.bin` та `flash_assets.bin`.

### 3. Оновлення іконок статусу dashboard
- `dashboard_usb` → блискавка (індикатор живлення).
- `dashboard_jaam` → мигалка (індикатор підключення до сервера тривоги).

### 4. Підвищення версій компонентів
- **ESPHome Firmware**: `v2.4.2`
- **GD32 Coprocessor Firmware**: `v1.3.4` (`0x0134`)
- **Graphic Assets Container**: 52 активних асети (`21,178` байтів)

## Хеш-суми бінарних файлів (Artifact Checksums)
Automated by GitHub Actions CI.
