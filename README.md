# RTOS_from_Scratch
Build Your Own RealTime OS (RTOS) on ARM 1

step1: with generic Cortex M4 user guide document called DUI0553A_cortex_m4_dgug, we would find the registers associated with a systick timer and configure it appropriately

step2: we would downlaod the documents specific to our particular ARM Cortex Microcontroller, in my case STM32F401CCU6
    A) Download the stm32f01ccu6 Reference Manual -> document starts with RMxxxx.pdf 
    B) Download the stm32f01ccu6 Datasheet        -> document starts with DSxxxx.pdf, datasheet gives us a block diagram of the entire microcontroller, the electrical characteristics of the microcontroller, the memory demarcations of the microcontroller, etc..
    example: we need the datasheet as we will find a particular Bus that's a peripheral is connected to. So for instance, we would go to the datasheet and see which bus the ADC is connected to. Once we located a bus, we would go to the reference manual to find out how to enable the bus and which particular bits inside the bus corresponds to this particular ADC module that we want to enable. so that is the datasheet document
    C) Download the BlackPill Development board from WeAct studio https://github.com/WeActStudio/WeActStudio.MiniSTM32F4x1/tree/master -> Document represents the BlackPill devlopment board all components including the Microcontroller STM32F401ccu6
