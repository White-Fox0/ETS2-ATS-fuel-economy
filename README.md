# ETS2 / ATS: справочник грузовиков и расход топлива

Одна HTML-страница для Euro Truck Simulator 2 и American Truck Simulator (версия 1.61).
Работает в браузере, ничего устанавливать не нужно. Данные взяты из файлов игры:
шасси, двигатели с кривыми момента, КПП, шины.

## Возможности

- Переключение ETS2 / ATS, русский / английский, единицы км/ч, т, л или mph, lb, gal.
- Подбор самой экономичной сборки под груз, прицеп и скорость:
  на любой передаче любой КПП обороты в начале полки момента (запас задаётся), заданный подъём держит.
- Расход топлива по формуле самой игры (режим «Реалистичный расход топлива»).
- Сравнение до четырёх сборок; выбор передачи, скорость в начале и в конце полки.
- Копирование блока `vehicle_accessory` для сохранения (двигатель, КПП с ретардером и без).

## Как игра считает расход

При включённом «Реалистичном расходе топлива»:

    л/с = consumption_coef × 3.95·10⁻⁹ × об/мин × M × (1 + 0.25 × (об/мин / 1150 − 1)²)

- M — момент двигателя плюс внутреннее трение (по умолчанию 20 Н·м на литр объёма, растёт с оборотами).
- Выгоднее держать низкие обороты в начале полки момента.
- `consumption_coef` обычно 1.0; в ATS у некоторых двигателей он ниже: от 6 до 11% меньше топлива.
- Навык «Экономичное вождение» в этом режиме на расход не влияет, только на оценку запаса хода.

При выключенном реалистичном расходе топливо списывается по норме
(32 л/100 км с прицепом при максимальном навыке), и тогда навык работает.

Сверка с реальными рейсами: расхождение от −6% до +14% в зависимости от дороги.
Это оценка для ровной дороги: подъёмы, разгоны и торможения учитываются поправкой.

---

# ETS2 / ATS: truck reference and fuel consumption

A single HTML page for Euro Truck Simulator 2 and American Truck Simulator (version 1.61).
Runs in the browser, nothing to install. Data comes from the game files:
chassis, engines with torque curves, gearboxes, tyres.

## Features

- Switch ETS2 / ATS, Russian / English, units km/h, t, L or mph, lb, gal.
- Finds the most economical build for a cargo, trailer and speed:
  any gear of any gearbox at the start of the torque plateau (the margin is adjustable), holding the set grade.
- Fuel consumption by the game's own formula ("Realistic fuel consumption" mode).
- Compare up to four builds; gear choice, speed at the start and end of the plateau.
- Copy a `vehicle_accessory` block for the save (engine, gearbox with or without retarder).

## How the game calculates fuel

With "Realistic fuel consumption" on:

    L/s = consumption_coef × 3.95·10⁻⁹ × rpm × M × (1 + 0.25 × (rpm / 1150 − 1)²)

- M is engine torque plus internal friction (20 N·m per litre of displacement by default, rising with rpm).
- Low rpm at the start of the torque plateau is the most economical.
- `consumption_coef` is usually 1.0; some ATS engines have a lower one: 6 to 11% less fuel.
- In this mode the Eco driving skill does not change consumption, only the range estimate.

With realistic consumption off, fuel is taken at a fixed rate
(32 L/100 km with a trailer at the maximum skill level), and then the skill does work.

Checked against real trips: −6% to +14% depending on the road.
The estimate is for a flat road; grades, acceleration and braking are covered by a correction.

## Disclaimer

Not affiliated with SCS Software. Specifications and names come from the game files
and belong to SCS Software.
