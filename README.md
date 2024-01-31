# knight-rider
 Project made with STM32F407VG Discovery Kit, which enables the LEDs to flash sequentially

 'void gpioConfig()' Function: This function is used to configure GPIO pins.The RCC_APB2PeriphClockCmd function provides a clock signal to the GPIOB port.
 Then, a structure named GPIOInitStructure of type GPIO_InitTypeDef is created, and the configuration of GPIO pins is done through this structure.
 In this example, the pins in the GPIOB port (0, 1, and 2) are configured in output mode (GPIO_Mode_Out_PP) and at a speed of 50 MHz (GPIO_Speed_50MHz)
 
 void gpioConfig(){
    GPIO_InitTypeDef GPIOInitStructure;
    
    RCC_APB2PeriphClockCmd(RCC_APB2Periph_GPIOB, ENABLE);
    
    GPIOInitStructure.GPIO_Mode = GPIO_Mode_Out_PP;
    GPIOInitStructure.GPIO_Pin = GPIO_Pin_0 | GPIO_Pin_1 | GPIO_Pin_2;
    GPIOInitStructure.GPIO_Speed = GPIO_Speed_50MHz;
    
    GPIO_Init(GPIOB, &GPIOInitStructure);
}

In this way, the code represents a program where three LEDs connected to the microcontroller are sequentially turned on and off using GPIO pins.