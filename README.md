# STM32F103-ATLAS
   Adaptación del microcontrolador STM32F103 conocido como BLUEPILL a la I/O BOARD ATLAS

   Es uno de los microcontroladores de la gama STM32 más usado, y optamos por adaptarlo a I/O BOARD ATLAS:
   
#   La base del diseño esta creada en la siguiente demo VGA PARA STM32F103:

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

Diseño propuesto más 6 pines en el bus 2x20, y 2 pines extra para tener un diseño QSPI.

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


Diseño del recolocador STM32F103 en I/O BOARD ATLAS.

---


![STM32](https://github.com/AtlasFPGA/STM32F103-ATLAS/blob/main/FOTOS/stm32f103-blue-pill-pinout.png)
