# UTS IoT

Starter IoT code for Microcontroller and IoT class.

## 📌 Pin

```cpp
#define led 2
#define buzzer 25
#define relay 26
#define button 19
#define pot 34
#define pinservo 23
#define trig 5
#define echo 18
```

I2C:

* SDA = 21
* SCL = 22

## 📚 Library

```cpp
#include <Arduino.h>
#include <Wire.h>
#include <WiFi.h>
#include <HTTPClient.h>
#include <WiFiClientSecure.h>
#include <ESP32Servo.h>
#include <LiquidCrystal_I2C.h>
#include <Adafruit_GFX.h>
#include <Adafruit_SSD1306.h>
#include <BH1750.h>
```

## ⚙️ Function

```text
readFirebaseSwitch(path)
= membaca status switch dari Firebase

cekFirebase()
= mengecek koneksi Firebase

kirimThingSpeak(field, data)
= mengirim data ke field tertentu di ThingSpeak

bacaAnalog(pin)
= membaca nilai ADC dari sensor analog

bacaBH1750()
= membaca intensitas cahaya dalam lux

setupOLED()
= inisialisasi OLED

setupLCD()
= inisialisasi LCD

setupServo()
= inisialisasi servo dan posisi awal

setupBH1750()
= inisialisasi sensor BH1750
```

## ☁️ Firebase

```cpp
#define path1 "/fatim_ayu/switch1.json"
// #define path2 "/fatim_ayu/switch2.json"
// #define path3 "/fatim_ayu/switch3.json"
```

Contoh:

```cpp
int switch1 = readFirebaseSwitch(path1);
```

`true` → `1`
`false` → `0`

## 📊 ThingSpeak

```cpp
#define field1 1
// #define field2 2
// #define field3 3
```

Contoh:

```cpp
kirimThingSpeak(field1, data);
```

Untuk mengirim:

* `field1` → data 1
* `field2` → data 2
* `field3` → data 3

Interval:

```cpp
const unsigned long thingspeak_interval = 15000;
```

= 15 detik.

## 🔌 Basic Function

```text
digitalWrite(pin, HIGH)
= menyalakan output

digitalWrite(pin, LOW)
= mematikan output

digitalRead(pin)
= membaca input digital

analogRead(pin)
= membaca nilai analog

map(value, fromLow, fromHigh, toLow, toHigh)
= mengubah range nilai

constrain(value, min, max)
= membatasi nilai

delay(ms)
= memberi jeda

millis()
= membaca waktu sejak ESP32 mulai berjalan
```

## ⚙️ Servo

```cpp
servo.write(sudut);
```

= mengatur sudut servo.

```cpp
servo.setPeriodHertz(50);
```

= mengatur frekuensi servo 50 Hz.

## 🖥️ OLED

```cpp
oled.clearDisplay();
```

= membersihkan layar.

```cpp
oled.setCursor(x, y);
```

= menentukan posisi tulisan.

```cpp
oled.setTextSize(size);
```

= mengatur ukuran tulisan.

```cpp
oled.print(data);
```

= menulis data ke buffer OLED.

```cpp
oled.display();
```

= menampilkan buffer ke OLED.

## 📟 LCD

```cpp
lcd.init();
```

= inisialisasi LCD.

```cpp
lcd.backlight();
```

= menyalakan backlight.

```cpp
lcd.setCursor(x, y);
```

= menentukan posisi tulisan.

```cpp
lcd.print(data);
```

= menampilkan data.

## 💡 BH1750

```cpp
lightMeter.begin();
```

= inisialisasi BH1750.

```cpp
lightMeter.readLightLevel();
```

= membaca intensitas cahaya dalam lux.

## 📡 WiFi

```cpp
WiFi.begin(ssid, password);
```

= menghubungkan ESP32 ke WiFi.

```cpp
WiFi.status();
```

= mengecek status koneksi WiFi.

```cpp
WiFi.localIP();
```

= mengambil IP address ESP32.

## 🔄 Bas
