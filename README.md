# EXPERIMENT--03-INTERFACING-AN16X2-LCD-DISPLAY-WITH-ARM AND DISPLAY STRING


 ## Aim: To Interface a 16X2 LCD display to ARM controller  , and simulate it in Proteus 
## Components required: STM32 CUBE IDE, Proteus 8 simulator .
## Theory 
The full form of an ARM is an advanced reduced instruction set computer (RISC) machine, and it is a 32-bit processor architecture expanded by ARM holdings. The applications of an ARM processor include several microcontrollers as well as processors. The architecture of an ARM processor was licensed by many corporations for designing ARM processor-based SoC products and CPUs. This allows the corporations to manufacture their products using ARM architecture. Likewise, all main semiconductor companies will make ARM-based SOCs such as Samsung, Atmel, TI etc.

What is an ARM7 Processor?
ARM7 processor is commonly used in embedded system applications. Also, it is a balance among classic as well as new-Cortex sequence. This processor is tremendous in finding the resources existing on the internet with excellence documentation offered by NXP Semiconductors. It suits completely for an apprentice to obtain in detail hardware & software design implementation.
 STM32F401xB STM32F401xC ARM® Cortex®-M4 32b MCU+FPU, 105 DMIPS, 256KB Flash/64KB RAM, 11 TIMs, 1 ADC, 11 comm.
interfaces Datasheet - production data Features
• Core: ARM® 32-bit Cortex®-M4 CPU with FPU, Adaptive real-time accelerator (ART Accelerator™) allowing 0-wait state execution from Flash memory, frequency up to 84 MHz, memory protection unit, 105 DMIPS/ 1.
25 DMIPS/MHz (Dhrystone 2.
1), and DSP instructions
• Memories – Up to 256 Kbytes of Flash memory – Up to 64 Kbytes of SRAM


   ## LCD 16X2 
   16×2 LCD is named so because; it has 16 Columns and 2 Rows. There are a lot of combinations available like,
   8×1, 8×2, 10×2, 16×1, etc. But the most used one is the 16*2 LCD, hence we are using it here.

All the above mentioned LCD display will have 16 Pins and the programming approach is also the same and hence the choice is left to you. 
Below is the Pinout and Pin Description of 16x2 LCD Module:
<img src="https://user-images.githubusercontent.com/36288975/233858086-7b1a88a2-f941-475c-86c2-b3bae68bdf7e.png" width="500">
<img src="https://user-images.githubusercontent.com/36288975/233857710-541ac1c2-786c-4dfc-b7b5-e3a4868a9cb6.png" width="500">
<img src="https://user-images.githubusercontent.com/36288975/233857733-05df5dbf-1a1e-479e-85bb-8014a39ad878.png" width="500">


4-bit and 8-bit Mode of LCD:

The LCD can work in two different modes, namely the 4-bit mode and the 8-bit mode. In 4 bit mode we send the data nibble by nibble, first upper nibble and then lower nibble. For those of you who don’t know what a nibble is: a nibble is a group of four bits, so the lower four bits (D0-D3) of a byte form the lower nibble while the upper four bits (D4-D7) of a byte form the higher nibble. This enables us to send 8 bit data.

Whereas in 8 bit mode we can send the 8-bit data directly in one stroke since we use all the 8 data lines.

 8-bit mode is faster and flawless than 4-bit mode. But the major drawback is that it needs 8 data lines connected to the microcontroller. This will make us run out of I/O pins on our MCU, so 4-bit mode is widely used. No control pins are used to set these modes. 
 LCD Commands:

There are some preset commands instructions in LCD, which we need to send to LCD through some microcontroller. Some important command instructions are given below:

Hex Code

Command to LCD Instruction Register

0F

LCD ON, cursor ON

01

Clear display screen

02

Return home

04

Decrement cursor (shift cursor to left)

06

Increment cursor (shift cursor to right)

05

Shift display right

07

Shift display left

0E

Display ON, cursor blinking

80

Force cursor to beginning of first line

C0

Force cursor to beginning of second line

38

2 lines and 5×7 matrix

83

Cursor line 1 position 3

3C

Activate second line

08

Display OFF, cursor OFF

C1

Jump to second line, position 1

OC

Display ON, cursor OFF

C1

Jump to second line, position 1

C2

Jump to second line, position 2
 
## Procedure:

1. Click on **STM32CubeIDE**, the following screen will appear:  
   <img src="https://user-images.githubusercontent.com/36288975/226189166-ac10578c-c059-40e7-8b80-9f84f64bf088.png" width="500">

2. Click on **File**, then click on **New STM32 Project**:  
   <img src="https://user-images.githubusercontent.com/36288975/226189215-2d13ebfb-507f-44fc-b772-02232e97c0e3.png" width="500">  
   <img src="https://user-images.githubusercontent.com/36288975/226189230-bf2d90dd-9695-4aaf-b2a6-6d66454e81fc.png" width="500">

3. Select the target to be programmed as shown below and click on **Next**:  
   <img src="https://user-images.githubusercontent.com/36288975/226189280-ed5dcf1d-dd8d-43ae-815d-491085f4863b.png" width="500">

4. Select the program name:  
   <img src="https://user-images.githubusercontent.com/36288975/226189316-09832a30-4d1a-4d4f-b8ad-2dc28f137711.png" width="500">

5. The corresponding .ioc file will be generated automatically:  
   <img src="https://user-images.githubusercontent.com/36288975/226189378-3abbdee2-0df6-470f-a3cd-79c74e3d3ad8.png" width="500">

6. Select the appropriate pins as GPIO, IN or OUT, USART, or required options, and configure:  
   <img src="https://user-images.githubusercontent.com/36288975/226189403-f7179f1a-3eae-4637-826b-ab4ec35ba1e1.png" width="500">  
   <img src="https://user-images.githubusercontent.com/36288975/226189425-2b2414ce-49b3-4b61-a260-c658cb2e4152.png" width="500">

7. Press `Ctrl + S`, and the C program will be generated automatically:  
   <img src="https://user-images.githubusercontent.com/36288975/226189443-8b43451d-0b14-47e4-a20b-cc09c6ad8458.png" width="500">  
   <img src="https://user-images.githubusercontent.com/36288975/226189450-85ffa969-2ffb-4788-81e5-72d60fdda0f1.png" width="500">

8. Edit the program as required:  
   <img src="https://user-images.githubusercontent.com/36288975/226189461-a573e62f-a109-4631-a250-a20925758fe0.png" width="500">

9. Add necessary library files for the LCD 16x2, write the program, and use **Project** > **Build All**:  
   <img src="https://user-images.githubusercontent.com/36288975/226189554-3f7101ac-3f41-48fc-abc7-480bd6218dec.png" width="500">

10. Once the project is built:  
    <img src="https://user-images.githubusercontent.com/36288975/226189577-c61cc1eb-3990-4968-8aa6-aefffc766b70.png" width="500">

11. Click on the **Debug** option:  
    <img src="https://user-images.githubusercontent.com/36288975/226189625-37daa9a3-62e9-42b5-a5ce-2ac63345905b.png" width="500">

### Creating a Proteus Project and Running the Simulation

12. Create a new Proteus project and place **STM32F40xx**, the same MCU for which the project was created in STM32CubeIDE.

13. Create the circuit as per the requirement, as shown below:  
    <img src="https://user-images.githubusercontent.com/36288975/233856847-32bea88a-565f-4e01-9c7e-4f7ed546ddf6.png" width="500">

14. Double-click on the MCU part to open settings. Next to the **Program File** option, give the full path to the Hex file generated using STM32CubeIDE. Set the external crystal frequency to 8 MHz and click **OK** to save changes:  
   14. Double-click on the MCU part to open settings. Next to the **Program File** option, give the full path to the Hex file generated using STM32CubeIDE. Set the external crystal frequency to 8 MHz and click **OK** to save changes:  
    <img src="https://engineeringxpert.com/wp-content/uploads/2022/04/26.png" width="500">


15. Click on **Debug** and simulate using the simulation option as shown below:  
    <img src="https://user-images.githubusercontent.com/36288975/233856904-99eb708a-c907-4595-9025-c9dbd89b8879.png" width="500">


## CIRCUIT DIAGRAM 
<img src="https://user-images.githubusercontent.com/36288975/233857974-bda6200e-4f88-4e7b-b189-4da80210fa23.png" width="500">



## STM 32 CUBE PROGRAM :
```c
#include "main.h"
#include "lcd.h"
int main(void)
{
  HAL_Init();
  SystemClock_Config();
  MX_GPIO_Init();
  Lcd_PortType ports[] = {GPIOA,GPIOA,GPIOA,GPIOA};
  Lcd_PinType pins[] = {GPIO_PIN_3,GPIO_PIN_2,GPIO_PIN_1,GPIO_PIN_0};
  Lcd_HandleTypeDef lcd;
  lcd = Lcd_create(ports,pins,GPIOB,GPIO_PIN_0,GPIOB,GPIO_PIN_1,LCD_4_BIT_MODE);
  Lcd_cursor(&lcd,0,1);
  Lcd_string(&lcd,"A.R.Basil");
  Lcd_cursor(&lcd,1,1);
  Lcd_string(&lcd,"212223040002");
  while (1)
  {

  }

}
```




## Output Screenshots of Proteus:
<img src="https://github.com/user-attachments/assets/7fed4a38-414d-4190-959c-c3ed0ca682a6" width="500">


 
## Circuit Diagram (Export the graphics to PDF and add the screenshot here):
<img src="https://github.com/user-attachments/assets/03cff9af-0c5f-4e95-821a-e2f7541fde50" width="500">


 
## Result :
Interfacing a lcd display with ARM microcontroller are simulated in proteus and the results are verified.

