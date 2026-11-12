# Twin Baby Logger

An Arduino Uno project to log feeding, vitamin D, nasal spray and diaper
changes for two babies. Entries are saved to an SD card (`BABY.CSV`) and shown
on a 16x2 LCD keypad shield. It also watches the room temperature and humidity
and reminds you when a feed or diaper change is due.

## Features

- Log bottle milk (with amount), vitamin D, nasal spray and diaper changes
- **Earlier Entry**: log something that happened a while ago
- **Daily Summary** and **History** by 24-hour feeding day (08:00 to 08:00)
- Last feeding (time and amount) and last diaper change
- Reminders: feed (2.5 h), diaper (12 h), vitamin D
- Room alerts: too cold, too warm (above 25 C), dry or damp air
- Buzzer ON/OFF in the main menu (OFF = no reminders or alerts pop up)
- Undo the last entries
- Clock is restored from the last record after a power cut
- Clock with room temperature shows by itself when the device is idle

## Hardware

| Part | Connection |
|---|---|
| Arduino Uno | |
| LCD keypad shield (16x2) | uses pins 4-9 and A0 |
| SD card module | CS = D3, MOSI = D11, MISO = D12, SCK = D13 |
| Buzzer | D2 |
| AHT20 (temperature, humidity) | I2C: SDA = A4, SCL = A5 |
| BMP280 (pressure) | I2C: SDA = A4, SCL = A5 |

## Keys

UP / DOWN / RIGHT = move or change, SELECT = select, LEFT = back.

## Build

1. Install the Arduino IDE.
2. Open `twin_baby_logger/twin_baby_logger.ino`.
3. Board: **Arduino Uno**. All libraries used (LiquidCrystal, SPI, SD, Wire,
   EEPROM) come with the Arduino IDE.
4. Upload.

The sketch uses almost all of the Uno's program memory (limit 32,256 bytes),
so new features may need others to be removed.

## SD card

Format the card as FAT16 or FAT32. The log is written to `BABY.CSV`:

```
Date,Time,Baby,Activity,Value
12-Nov-2026,09:05:03,Fariz,Milk,140
```
<img width="4624" height="3472" alt="IMG_20261111_233604" src="https://github.com/user-attachments/assets/9876cb19-ff1b-4ab3-94ca-4c8a0e086a8a" />
<img width="4624" height="3472" alt="IMG_20261111_233546" src="https://github.com/user-attachments/assets/e1fdf906-4df8-433f-bc1f-d83fc7bbf487" />
<img width="1080" height="1440" alt="image-1794413829108" src="https://github.com/user-attachments/assets/0e8184d2-157c-471a-bc26-285e107cd455" />
<img width="4624" height="3472" alt="IMG_20261111_233632" src="https://github.com/user-attachments/assets/e6440bf4-572c-4e81-a3a1-aa74900aa5fb" />
