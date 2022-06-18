# v2 - work in progress
Additions/improvements are going to be: backlighting, integrated microcontroller, more comfortable design, better looking design. 

## Choice of components
* STM32F072VBT6: This is the microchip I want to use. The choice was inspired by [this](https://github.com/KoBussLLC/grabert-hardware) tutorial. The important part is that it has 87 I/Os and it has a 48 MHz internal oscillator. Thus a keyboard matrix with diodes and an external oscillator is not neccesary, which reduces the amount of components on the pcb.
* 