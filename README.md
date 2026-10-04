# UTS IoT

Starter IoT code for Microcontroller and IoT class.

## Features

* ESP32
* WiFi
* Firebase Realtime Database
* ThingSpeak
* OLED SSD1306
* LCD I2C
* Servo
* BH1750
* Analog Sensor
* Digital I/O

## Functions

| Function                       | Description                                                               |
| ------------------------------ | ------------------------------------------------------------------------- |
| `readFirebaseSwitch(path)`     | Membaca status switch dari Firebase dan mengembalikan nilai `1` atau `0`. |
| `cekFirebase()`                | Mengecek koneksi ESP32 ke Firebase.                                       |
| `kirimThingSpeak(field, data)` | Mengirim data ke field tertentu pada ThingSpeak.                          |
| `bacaAnalog(pin)`              | Membaca nilai ADC dari pin analog.                                        |
| `bacaBH1750()`                 | Membaca intensitas cahaya dari BH1750 dalam satuan lux.                   |
| `setupOLED()`                  | Menginisialisasi OLED SSD1306.                                            |
| `setupLCD()`                   | Menginisialisasi LCD I2C.                                                 |
| `setupServo()`                 | Menginisialisasi servo dan mengatur posisi awalnya.                       |
| `setupBH1750()`                | Menginisialisasi sensor BH1750.                                           |

## Common Functions

| Function                   | Description                                               |
| -------------------------- | --------------------------------------------------------- |
| `digitalWrite(pin, value)` | Mengatur output digital menjadi HIGH atau LOW.            |
| `digitalRead(pin)`         | Membaca kondisi input digital.                            |
| `analogRead(pin)`          | Membaca nilai analog/ADC.                                 |
| `map()`                    | Mengubah nilai dari satu rentang ke rentang lainnya.      |
| `constrain()`              | Membatasi nilai agar tetap berada dalam rentang tertentu. |
| `delay(ms)`                | Memberikan jeda selama waktu tertentu.                    |
| `millis()`                 | Mengambil waktu sejak ESP32 mulai berjalan.               |

## Servo

| Function                   | Description                             |
| -------------------------- | --------------------------------------- |
| `servo.attach(pin)`        | Menghubungkan servo ke GPIO tertentu.   |
| `servo.write(angle)`       | Mengatur sudut servo.                   |
| `servo.setPeriodHertz(50)` | Mengatur frekuensi servo menjadi 50 Hz. |

## OLED

| Function                   | Description                        |
| -------------------------- | ---------------------------------- |
| `oled.clearDisplay()`      | Membersihkan buffer tampilan OLED. |
| `oled.setCursor(x, y)`     | Mengatur posisi tulisan.           |
| `oled.setTextSize(size)`   | Mengatur ukuran teks.              |
| `oled.setTextColor(color)` | Mengatur warna teks.               |
| `oled.print(data)`         | Menulis data ke buffer OLED.       |
| `oled.display()`           | Menampilkan buffer ke layar OLED.  |

## LCD

| Function              | Description                 |
| --------------------- | --------------------------- |
| `lcd.init()`          | Menginisialisasi LCD.       |
| `lcd.backlight()`     | Mengaktifkan backlight LCD. |
| `lcd.setCursor(x, y)` | Mengatur posisi tulisan.    |
| `lcd.print(data)`     | Menampilkan data pada LCD.  |

## BH1750

| Function                      | Description                          |
| ----------------------------- | ------------------------------------ |
| `lightMeter.begin()`          | Menginisialisasi sensor BH1750.      |
| `lightMeter.readLightLevel()` | Membaca intensitas cahaya dalam lux. |

## WiFi

| Function                     | Description                           |
| ---------------------------- | ------------------------------------- |
| `WiFi.begin(ssid, password)` | Menghubungkan ESP32 ke jaringan WiFi. |
| `WiFi.status()`              | Mengecek status koneksi WiFi.         |
| `WiFi.localIP()`             | Mengambil alamat IP ESP32.            |

## Firebase

| Item                      | Description                                         |
| ------------------------- | --------------------------------------------------- |
| `host`                    | URL Firebase Realtime Database.                     |
| `path1`, `path2`, `path3` | Path untuk masing-masing data/switch pada Firebase. |
| `readFirebaseSwitch()`    | Membaca nilai switch dari Firebase.                 |
| `cekFirebase()`           | Mengecek koneksi ke Firebase.                       |

## ThingSpeak

| Item                         | Description                                      |
| ---------------------------- | ------------------------------------------------ |
| `api_key`                    | Write API Key untuk mengirim data ke ThingSpeak. |
| `field1`, `field2`, `field3` | Field tujuan data pada ThingSpeak.               |
| `thingspeak_interval`        | Interval pengiriman data ke ThingSpeak.          |
| `kirimThingSpeak()`          | Mengirim data ke ThingSpeak.                     |

## I2C

Default I2C configuration:

* **SDA:** GPIO 21
* **SCL:** GPIO 22
* **OLED:** `0x3C`
* **LCD:** `0x27`

## Notes

Starter ini dibuat sebagai template dasar untuk praktikum dan UTS.
Bagian `void loop()` dapat disesuaikan dengan kebutuhan soal.
