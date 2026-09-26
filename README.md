# FNIRSI 2D15P — UA mod 1.0

Неофіційна модифікація прошивки осцилографа **FNIRSI 2D15P**: **українська мова інтерфейсу** та **виправлений англійський переклад**.
Unofficial modification of the **FNIRSI 2D15P** firmware: **Ukrainian interface language** and **corrected English translation**. *English version below.*

> ⚠️ **Лише для прошивки V2.7.0.7** (файл `2D15P_V2.7.0.7_260826.bin`, CRC32 `B43E8C2D`).
> Патч перевіряє контрольну суму і **не застосується** до іншої версії. Не намагайтеся обійти цю перевірку: зміни прив'язані до точних адрес саме цієї версії, і на іншій прошивці прилад може не запуститися.

---

## Українською

### Що зроблено
| | |
|---|---|
| Перекладено написів інтерфейсу | **115** + 9 поза таблицями мов |
| Виправлено англійських написів | **29** |
| Додано літер у шрифти | **74** символи × **6** шрифтів = **444** гліфи |
| Змін у розмітці меню | меню в **3** ряди + **13** карт дотиків |
| Розмір патча | ~30 КБ, лише власні зміни, без коду FNIRSI |

- **Українська мова** на місці китайської. У виборі мови: «Українська» / «English». Після скидання налаштувань прилад запускається українською.
- **Кирилиця в усіх шести шрифтах** приладу, підібрана за висотою й товщиною під заводську латиницю (гарнітура Fixel).
- **Виправлена англійська**, наприклад: «Level» → «Horizontal», «Ramp» → «Triangle», «Skew» → «Offset», «Regarding» → «About», «Auto Shut» → «Auto Off», «2.bmpSaving...» → «2.bmp saving...».
- **Верхнє меню в три ряди**: повні назви вміщаються і більше не перекривають підменю, зони дотику кнопок розширено.
- Рядок стану: короткі назви режимів синхронізації, які не переносяться.
- У «Про прилад» видно версію моду: «Версія (UA-мод 1.0)».

### Що НЕ змінено
- **Вимірювання, калібрування, генератор, мультиметр** працюють за заводською логікою. Мод змінює лише тексти, шрифти й розмітку меню.
- Китайської мови в моді немає.
- Заводські вади (див. нижче) не виправлені.

### Встановлення
**Що потрібно:** прилад, заряджений хоча б наполовину, USB-кабель, комп'ютер або телефон.

1. Завантажте з сайту FNIRSI **офіційну** прошивку V2.7.0.7 і розпакуйте архів. Потрібен файл `2D15P_V2.7.0.7_260826.bin`.
2. Відкрийте **Rom Patcher JS**: https://www.marcrobledo.com/RomPatcher.js/ (працює в браузері, і на телефоні теж, нічого встановлювати не треба).
3. У полі «ROM file» оберіть файл прошивки, у полі «Patch file» — `2D15P_V2.7.0.7_UA-mod-1.0.bps`, натисніть «Apply patch» і збережіть результат.
   *Альтернатива для комп'ютера: програма Floating IPS (Flips).*
4. Переконайтеся, що збережений файл називається **точно** `2D15P_V2.7.0.7_260826.bin`. Якщо браузер додав до назви щось своє, перейменуйте. Для перевірки: CRC32 результату `4D482107`.
5. На приладі (заводська англійська версія): кнопка **Menu** → **USB Sharing** → **ON**. Прилад з'явиться на комп'ютері як USB-диск.
6. Скопіюйте файл у папку **`Upgrade file`** на цьому диску.
7. Вимкніть і увімкніть прилад. Оновлення встановиться саме, файл після цього зникне з диска.
8. **Settings → Language → «Українська»**.

### Як повернути заводську прошивку
Встановлення **повністю оборотне**.
- **Звичайний спосіб:** прошийте офіційний файл V2.7.0.7 так само, як описано вище (кроки 5–7).
- **Якщо прилад не запускається:** вимкніть його, **затисніть великий регулятор і коротко натисніть кнопку живлення**. Запуститься завантажувач, який незалежно від основної прошивки відкриється на комп'ютері як USB-диск. Скопіюйте офіційний файл у папку `Upgrade file` і перезапустіть прилад.

### Відомі заводські вади (у моді не виправлені)
- **Нижче ~4,19 МГц** амплітуда падає приблизно на 3 %, а у двоканальному режимі (250 МВиб/с) один фронт синуса запізнюється приблизно на 28 нс. Поріг рівно **2²² Гц = 4 194 304 Гц** і збігається з точкою, де частотомір у ПЛІС перемикає режим (вимірювання періоду ↔ підрахунок імпульсів). Мікроконтролер обробку сигналу за цим не змінює, тож причина **в ПЛІС** і в прошивці мікроконтролера не виправляється.
- Кнопка видалення в режимі перегляду знімка порожня (так само в англійській версії).
- «Trig'd», «Stop», «Roll» у рядку стану англійською в обох мовах.

### Відмова від відповідальності
Мод перевірено на одному приладі. Використовуєте на власний ризик. Автор не пов'язаний з FNIRSI. Відгуки й повідомлення про помилки — через розділ Issues цього репозиторію.

---

## English

> ⚠️ **For firmware V2.7.0.7 only** (`2D15P_V2.7.0.7_260826.bin`, CRC32 `B43E8C2D`).
> The patch checks the checksum and **will refuse** any other version. Do not try to bypass this: the changes target exact addresses of this version, and on other firmware the device may fail to boot.

### What's done
| | |
|---|---|
| UI strings translated | **115** + 9 outside the language tables |
| English strings corrected | **29** |
| Glyphs added to fonts | **74** characters × **6** fonts = **444** glyphs |
| Menu layout changes | **3**-row menu + **13** touch maps |
| Patch size | ~30 KB, own changes only, no FNIRSI code |

- **Ukrainian language** replaces Chinese (language menu: «Українська» / «English»). After a factory reset the device starts in Ukrainian.
- **Cyrillic in all six device fonts**, matched to the stock Latin height and weight (Fixel typeface).
- **Corrected English**, e.g. "Level" → "Horizontal", "Ramp" → "Triangle", "Skew" → "Offset", "Regarding" → "About", "Auto Shut" → "Auto Off", "2.bmpSaving..." → "2.bmp saving...".
- **Three-row top menu**: full labels fit and no longer cover the submenu; touch zones enlarged.
- About page shows the mod version: "Version (UA mod 1.0)".

### What's NOT changed
Measurement, calibration, generator and multimeter logic are stock. Only texts, fonts and menu layout are changed. Chinese is not available. Stock bugs below are not fixed.

### Installation
1. Download the **official** V2.7.0.7 firmware from FNIRSI and unzip it (`2D15P_V2.7.0.7_260826.bin`).
2. Open **Rom Patcher JS**: https://www.marcrobledo.com/RomPatcher.js/ (runs in the browser, phones included). Alternative: Floating IPS (Flips).
3. Select the firmware as "ROM file" and `2D15P_V2.7.0.7_UA-mod-1.0.bps` as "Patch file", click "Apply patch", save the result.
4. Make sure the result is named **exactly** `2D15P_V2.7.0.7_260826.bin` (CRC32 `4D482107`).
5. On the device: **Menu** button → **USB Sharing** → **ON**, copy the file into the **`Upgrade file`** folder, power cycle.
6. **Settings → Language → «Українська»** (or keep English).

### Reverting
Fully reversible. Flash the official V2.7.0.7 file the same way. If the device does not boot: power off, **hold the large knob and briefly press the power button** — the bootloader appears as a USB drive regardless of the main firmware.

### Known stock issues (not fixed)
- **Below ~4.19 MHz** the amplitude drops by about 3 %, and in dual-channel mode (250 MSa/s) one sine edge is delayed by about 28 ns. The threshold is exactly **2²² Hz = 4,194,304 Hz** and coincides with the FPGA frequency counter switching modes (period ↔ count). The MCU does not change signal processing based on it, so the cause is **in the FPGA** and cannot be fixed in the MCU firmware.
- Delete button in single-picture view has no label or icon (also in English).
- "Trig'd", "Stop", "Roll" in the status bar remain English.

### Disclaimer
Tested on one unit. Use at your own risk. Not affiliated with FNIRSI. Please report issues via the Issues tab.

---

## Credits / Ліцензії
- Cyrillic glyphs rendered from **Fixel Text** © 2023 MacPaw Way Ltd., **SIL Open Font License 1.1** (see `OFL-Fixel.txt`), converted to the device's bitmap format.
- Кириличні гліфи — з гарнітури **Fixel Text** © 2023 MacPaw Way Ltd., ліцензія **SIL Open Font License 1.1** (`OFL-Fixel.txt`), перетворено в растровий формат приладу.
- The original firmware is © FNIRSI and must be obtained from FNIRSI. The patch contains only the changes.
