# ESP-GIK
ESP-GIK - прошивка для пентеста и кибер безопасности , созданная для платформы esp32 имеющяя компактный интерфейс для дисплея и кнопок . Имеет встроенную модульную систему (WI-FI , BLUETOOTH , NRF24 (2.4G) , IR) .

<img width="1458" height="1855" alt="WhatsApp Image 2026-05-30 at 09 43 34" src="https://github.com/user-attachments/assets/9eaa42ec-a1b6-4fb1-ac5a-c5e4fd557438" />

Используйте этот код с остарожностью ! Автор не несёт ответвенность за ваши действия !

Функции:
1) WI-FI MENU:

   SCAN

   PACKET MONITOR

   ATTACK

2) BLUETOOTH MENU:

   SCAN

   GET-DEVICE-INFO

3) NRF24 MENU:

   JAMMER 2.4G

   SPECTRUM 2.4G

4) IR MENU:

   IR JAMMER

   TV-B-GONE

5) MAIN MENU:

   VERSION

   CREATOR

   CHANNEL

   WEB MENU

   TIME (STOPWATCH ⏱ , TIMER ⏲)

Компоненты для сборки:
1) esp32 s3 super mini (1 шт.) .
2) Oled display 1.3 , драйвер SH1106 (1 шт.) .
3) NRF24L01 (1 шт.) .
4) TP4056 (1 шт.) .
5) Ик светодиод (2 шт.) .
6) Транзистор BC547 (1 шт.) .                               
7) Резистор 1К (1 шт.) , резистор 10К (3 шт.) , резистор 47R (1 шт.) .
8) Тактовая кнопка (3 шт.) .
9) Кнопка вкл/выкл питания (1 шт.) .
10) АКБ 500-800mAh (1 .шт) .

Пометка: 

Если не хотите сами собирать схему для IR TRANSMITTERA , то можно просто 
использовать для этого готовый модуль с AliExpress .

После сборки на макетной плате у вас должно получится что то похожее на это:

<img width="1080" height="1210" alt="WhatsApp Image 2026-05-30 at 12 37 13" src="https://github.com/user-attachments/assets/5584d16a-6270-4f3a-ab38-7bcbed9d2bc5" />

Как загрузить прошивку 1 способ:
1) Перейдите во вкладку "Releases" и скачайте там три файла: 'bootloader' , 'partitions' и 'firmware.bin' .
2) Скачайте и установите программу [ESP Flash Dowload Tool] (https://espressif.com) .
3) Подключите плату esp32 к ПК через USB кабель (кабель должен иметь Data протокол) .
4) Откройте программу и выберите чип 'ESP32-S3' .
5) Зажмите на плате esp32 комбинацию кнопок boot , после reset , после этого отпустите обе кнопки и повторно нажмите boot .
6) Нажмите в программе кнопку CONNECT и выберите COM порт к которому подключена плата . 
7) Укажите пути к файлам и следующие адреса для прошивки в пустых строках:
   
sketch_may24b.ino.bootloader -> адрес 0x1000 

sketch_may24b.ino.partitions -> адрес 0x8000

sketch_may24b.ino -> адрес 0x10000

9) нажмите 'START' и дождитесь окончания прошивки .
10) После окончания прошивки перезагрузите плату нажав кнопку reset .

Как загрузить прошивку 2 способ:

Для второго способа можно воспользоваться моим Web Flasherom: https://tranzistor111.github.io/ESP-GIK-Web-flasher-/
Просто перейдите по ссылке , подключите плату к ПК и переведите её в режим прошивки (как это сделать написанно в 
первом способе) и нажмите CONNECT , после выберите COM порт и нажмите подключенение . После всех проделанных 
ранее монипуляций вам останется только нажать на кнопку FLASH и дождатся окончания загрузки прошивки на плату .

Поздравляю вы только , что прошили ESP-GIK !

Распиновка платы esp32 s3 super mini: 

<img width="682" height="690" alt="SghjfHJ3V2-682" src="https://github.com/user-attachments/assets/728993fb-9f0f-4c7b-8c48-faf6d86a7a1a" />

Схема устройства:

<img width="1080" height="861" alt="WhatsApp Image 2026-05-30 at 18 12 51" src="https://github.com/user-attachments/assets/275184bb-8ad8-4313-bed8-b83753826081" />

1) OLED 1.3:

   GND - GND
   
   VCC - +5V
   
   SCL - 7
   
   SDA - 6

2) NRF24L01:

   GND - GND

   VCC - 3.3V

   CE - 1

   CSN - 2

   SCK - 3

   MOSI - 4

   MISO - 5

3) BUTTONS:

   GND - GND - R1(10k) - SW1 - 8

   GND - GND - R2(10k) - SW2 - 9

   GND - GND - R3(10k) - SW3 - 10

4) IR TRANSMITTER:

   GND - GND

   RX(R4) - 11

   VCC(R5) - +5V

5) TP4056:

   BAT+ - +АККУМУЛЯТОРА 🔋 

   BAT- - -АККУМУЛЯТОРА 🔋

   OUT+ - КНОПКА ВКЛ/ВЫКЛ - +5V

   OUT- - GND 

Мой тик ток канал: https://www.tiktok.com/@tranzistor_misha?_r=1&_t=ZS-96k07YpY1MO 

Удачного вам использования прошивки ! По вопросам пишите мне в тик ток ! 



