# HTRAM Release v2.4.1

## Огляд релізу (Release Overview)
Реліз `v2.4.1` переводить клієнт повітряних тривог на сервісний WebSocket API JAAM (`/data_service_v1`), включає великий пакет room-dashboard/OTA змін із `#1`, і додає точкове візуальне оновлення статус-індикаторів dashboard (блискавка для живлення та мигалка для статусу JAAM).

## Основні зміни (Key Features & Improvements)

### 1. Міграція на сервісний WebSocket API JAAM (`/data_service_v1`)
- Клієнт `jaam_ws` переведено з `/data_fusion_v1` на `/data_service_v1` (`ws://ws.jaam.net.ua:80/data_service_v1`).
- Додано обов'язкову ідентифікацію сервісу (`service_id`, `service_name`, `website`, `contact`, `version`) і роботу через `hello:<JSON>`.
- Додано обробку сервісних кодів закриття з'єднання та оновлену стратегію reconnect/backoff.
- Виправлено кейс жовтого рівня тривоги при одночасному legacy-біті.

### 2. Room Dashboard + OTA пакет із `#1`
- В `main` увійшов великий пакет змін із merge-коміту `28eabe2`:
  - новий `room_dashboard` режим і пов'язані UI-асети;
  - окремі room-конфіги (`living`, `bedroom`, `office`, `kids-1`, `kids-2`) з власними OTA-артефактами;
  - доповнення CI/релізного пайплайна для складання й публікації room-бінарників.

### 3. Оновлення іконок статусу dashboard
- У коміті `fc6eebd` оновлено 2 іконки:
  - `dashboard_usb` → блискавка (індикатор живлення);
  - `dashboard_jaam` → мигалка (індикатор зв'язку з сервером тривоги).
- Оновлення включає SVG-джерела та відповідні 1-бітні маски для прошивки.

### 4. Підвищення версій компонентів
- **ESPHome Firmware**: `v2.4.1`
- **GD32 Coprocessor Firmware**: `v1.3.4` (`0x0134`)
- **Graphic Assets Container**: 52 активних асети (`21,178` байтів)

## Хеш-суми бінарних файлів (Artifact Checksums)
Automated by GitHub Actions CI.
