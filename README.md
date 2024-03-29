# STM32F103-ATLAS
   Adaptación del microcontrolador STM32F103 conocido como BLUEPILL a la I/O BOARD ATLAS
   Group ATLAS in Telegram: https://t.me/INICIATIVAATLAS

   Es uno de los microcontroladores de la gama STM32 más usado, y optamos por adaptarlo a I/O BOARD ATLAS:
   
###   La base del diseño esta creada en la siguiente demo VGA PARA STM32F103:

https://github.com/abelykh0/VGA-demo-on-bluepill

Vídeo asociado a esta demo en el controlador STM32:

<a href="http://www.youtube.com/watch?feature=player_embedded&v=97oakB1NX68
" target="_blank"><img src="http://img.youtube.com/vi/97oakB1NX68/0.jpg" 
alt="VGA Demo on Bluepill" width="480" height="360" border="10" /></a>

Uso del grabador STLINK, es necesario:

Señales disponibles en I/O BOARD ATLAS a disposición del STM32F103:

---

señales ATLAS| aclaración en STM32F103 | numero pines
| :--- | ---: | :---:
Señal VGA64 |Usamos en el STM32F103 un esquema de 64colores 222+HS+VS | 8
Señal JOYSTICK DB9 | En preparación ATARI-PADDLE-ATLAS  | 6
Señal SD SPI | las señales QPI se usan en modo SPI| 4
Señal PS2 TECLADO  | Protocolo PS/2 | 2
Señal PS2 RATÓN | Protocolo PS/2 | 2
Señal Sonido Estereo | sonido delta sigma_(12bits) o un pwm_(10bits)| 2
Señal Transmisión y Recepcion | RX TX sin gestión de flujo| 2
Señal EAR | Señal de entrada | 1

Pines disponibles en el Diseño con conectores en la I/O BOARD ATLAS 25 + 2 + 6:

Diseño propuesto más 6 pines en el bus 2x20, y 2 pines extra para tener un diseño QSPI, El microcontrolador STM32F103 tiene disponibles 30 señales.

señales ATLAS | Patillaje izquierda | patilaje derecha | señales ATLAS
| ---: | ---: | ---: | :---: 
PI_CS  | PB12  | GND | GND
PI_CLK  | PB13 | GND| GND
PI_MISO  | PB14 | +3V3 | +3V3
PI_MOSI| PB15 | RESET_B | RESET_STM32
KB_CLK | PA8 | PB11 | JOY_DOWN
KB_DATA | PA9 | PB10 | JOY_RIGHT
MOUSE_CLK | PA10 | PB1 | JOY_LEFT
MOUSE_DATA | PA11 | PB0 | HSYNC
EAR | PA12 | PA7 | AUDIO_R
SD_CS | PA15 | PA6  | AUDIO_L
SD_CLK | PB3 | PA5 | BLUE[1]
SD_MISO | PB4 | PA4 | BLUE[0]
SD_MOSI | PB5 | PA3 | GREEN[1]
VSYNC | PB6 | PA2 | GREEN[0]
JOY_P1| PB7 | PA1 | RED[1]
JOY_UP| PB8 | PA0| RED[0]
JOY_P2| PB9 | PC15 | OSC32 OUT
+5v| +5V | PC14 | OS32 IN
GND| GND | PC13 | TAMPER RTC
+3V3| +3V3 | VBAT| VBAT

Segunda asignación STM32F103 en la I/O BOARD ATLAS.

...


How to connect wires:

---

| PIN | Description |  Output |
| --- | ----------- | ------ |
| PA0 | Red 1 | VGA red 
| PA1 | Red 2 |  VGA red 
| PA2 | Green 1 |  VGA green 
| PA3 | Green 2 |  VGA green 
| PA4 | Blue 1 |  VGA blue 
| PA5 | Blue 2 |  VGA blue 
| PB0 | HSync |  VGA HSync 
| PB6 | VSync |  VGA VSync 
| G | Ground |  VGA Ground 


Diseño del recolocador STM32F103 en I/O BOARD ATLAS ya asignadas por la demo.

---


![STM32](https://github.com/AtlasFPGA/STM32F103-ATLAS/blob/main/FOTOS/stm32f103-blue-pill-pinout.png)
