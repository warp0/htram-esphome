# HTRAM Release v2.4.4

## Огляд релізу
Реліз `v2.4.4` виправляє некоректний стан статусних масок у room dashboard під час втрати мережі. Раніше іконки Wi‑Fi/Internet/JAAM могли залишатися зеленими навіть у офлайн-стані в симуляції, що маскувало реальний стан з'єднання.

## Основні зміни

### 1. Виправлення індикаторів мережі на room dashboard
- У `refresh_room_dashboard_status` індикатор `wifi_connected` тепер враховує `sim_override_net` у `indicator_mode < 0`.
- `internet_connected` тепер залежить від фактичного `wifi_connected`, а не лише від `internet_last_sync_ms`.
- `jaam_connected` тепер також залежить від `wifi_connected`, щоб JAAM-іконка не лишалась зеленою без Wi‑Fi.
- Офлайн-сценарій повторно перевірено у `htram-room-sim` з порівняльними скріншотами до/після.

### 2. Підвищення версій компонентів
- **ESPHome Firmware**: `v2.4.4`
- **GD32 Coprocessor Firmware**: `v1.3.4` (`0x0134`), без змін.
- **Graphic Assets Container**: без змін.

## Хеш-суми бінарних файлів
Генеруються GitHub Actions під час збірки релізу.
