# Transport Frames QGIS Plugin

Плагин добавляет в QGIS Processing набор методов библиотеки `transport_frames`.
Он позволяет подготовить Python-окружение и запускать расчеты графов, каркаса, оценки и индикаторов прямо в QGIS.

### Что делает плагин

- Разворачивает и использует Python-окружение для `transport_frames` (managed/custom mode).
- Строит графы улично-дорожной и интермодальной сети.
- Строит взвешенный транспортный каркас территории.
- Оценивает территории относительно транспортного каркаса.
- Считает индикаторы доступности, связанности, длин и плотностей.

### Где искать инструменты

- `Processing Toolbox -> Transport Frames`
- Группы алгоритмов:
- `Environment`
- `Graph`
- `Frame`
- `Grade`
- `Indicators`

### Алгоритмы по группам

#### Environment

- `Setup Python Environment`: создает/обновляет `venv` в профиле QGIS, устанавливает пакет и включает managed mode.
- `Environment Status`: показывает текущий режим и сохраненные пути к Python.

#### Graph

- `Get Drive Graph`: строит граф УДС по `OSM relation ID` или границе территории.
- `Add Roads`: добавляет новые дороги в существующий drive graph (`reg` обязателен).
- `Get Intermodal Graph`: строит интермодальный граф (общественный транспорт + пешие связи).

#### Frame

- `Get Weighted Frame`: строит взвешенный транспортный каркас по входному графу и опорным слоям.

#### Grade

- `Grade Territory`: присваивает оценку территориям по их положению относительно транспортного каркаса.

#### Indicators

- `Get Roads Length`: суммарная длина дорог по полигонам.
- `Get Roads Density`: плотность дорог по полигонам.
- `Get Roads Length by Type`: длины дорог по классам `reg`.
- `Get Railways Length`: длина железнодорожной сети по полигонам.
- `Get Connectivity`: показатель связности (медиана во времени).
- `Get Service Count`: количество сервисов в полигонах.
- `Get Service Accessibility`: доступность сервисов (время в минутах).
- `Get Service Count for Territory`: количество сервисов для выбранных территорий.
- `Get Service Accessibility for Territory`: доступность сервисов для выбранных территорий.

### Требования

- QGIS 3.x (минимум в метаданных: `3.0`).
- Python `3.11+` для настройки среды.

### Быстрый старт

1. Скачайте репозиторий как ZIP (Code → Download ZIP), затем в QGIS откройте Plugins → Manage and Install Plugins → Install from ZIP, выберите архив и нажмите Install Plugin (распаковка выполняется автоматически).
2. Запустите `Setup Python Environment` и установите `transport_frames` в managed environment.
3. Проверьте режим через `Environment Status`.
4. Постройте граф (`Get Drive Graph` или `Get Intermodal Graph`).
5. Запускайте `Frame`, `Grade` и нужные `Indicators`.

### Репозитории

- Upstream library (`transport_frames`): https://github.com/alexandermorozzov/tf