# v2
Additions/improvements are going to be: backlighting, integrated microcontroller, more comfortable design, better looking design. 

## Choice of components
* STM32F072VBT6: This is the microchip I want to use. The choice was inspired by [this](https://github.com/KoBussLLC/grabert-hardware) tutorial. The important part is that it has 87 I/Os and it has a 48 MHz internal oscillator. Thus a keyboard matrix with diodes and an external oscillator is not neccesary, which reduces the amount of components on the pcb.
* WS2812B-2020: This is the RGB LED I will use for the keyboard backlighting. There was tree main reasons for choosing this component. The first reason is the fact that it has an integrated decoupling capacitor, which reduces the amount of components on the pcb. The second reason is that it is an intelligent control LED which means that all LEDs can be controlled by a single port on the microcontroller. Lastly the input voltage on this chip can be as low as 2.7V. Which works very well with the chosen STM32F072VBT6 chip that normally uses VDD=3.3V.
