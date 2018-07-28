# STM32F7-Programming
Blinking LEDs on Nucleo-F767ZI Evaluation Board  
@author: Alpaslan Ersoz

@description

First Step: Setting Nucleo-F767ZI Board pins in CubeMX 
              Under Pinout Section,
              - RCC, High Speed Clock (HSE) is modified into Crystal/Ceramic Resonator.
              - In Nucleo-F767ZI, LED1 is connected with PB0; LED2 is connected with PB7; LED3 is connected with PB14. So, PB0, PB7, and 
                PB14 pins are set as GPIO_Output (Left click on pins and select GPIO_Output) 
              Under Configuration Section
              - In RCC Configuration menu, enable RCC interrupt in NVIC Settings and then select OK.

Second Step: Generating C Code of the project
              - Select on Project and Generate Code in menu bar.
              - Then, automatic saving window will appear. Under Project Menu, you can write a file name whatever you want. Toolchain/IDE should be MDK-ARM 5 
                if you are using Keil uVision5 as an IDE. Under Code Generator Menu, you can check 'Generate necessar files'. Then, select OK for saving and 
                generating C code in Keil uVision.
                
Third Step: Write C Code in Keil uVision 5 IDE and Run
              - In Application User File, you can edit and add C codes in main.c file.
              - After selecting main.c file, you can write the code what I shared at the bottom of page.
	      - We see that port and pin numbers are defined based on connection of LEDs on the board.
              - In Project menu bar, you can run the codes with selecting 'Rebuild All Target File' choice.
              - If there is no error, you can load the codes into the board with selecting 'Download' under 'Flash' in menu toolbar.
                
                ...
              
              while (1)
              {

              /* USER CODE END WHILE */

              /* USER CODE BEGIN 3 */
	              	HAL_GPIO_TogglePin(GPIOB, GPIO_PIN_0);
                   /* Insert delay 100 ms */
                  HAL_Delay(100);
		              HAL_GPIO_TogglePin(GPIOB, GPIO_PIN_7);
                   /* Insert delay 100 ms */
                  HAL_Delay(100);
	              	HAL_GPIO_TogglePin(GPIOB, GPIO_PIN_14);
                   /* Insert delay 100 ms */
                  HAL_Delay(100);

               }
               /* USER CODE END 3 */
               
               ...
               
               
          
                
