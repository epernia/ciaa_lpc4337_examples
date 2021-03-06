# CIAA PROJECT LPC4337 EXAMPLES

Examples working with [CIAA project repository](../../../ciaa_project).

## Supported boards
- CIAA-NXP (LPC4337).
- EDU-CIAA-NXP (LPC4337).

## Supported toolchains
- gcc-arm-none-eabi

## Usage
- Make sure you have an ```arm-none-eabi-*``` toolchain configured in your ```PATH```. If you don't have it, download [GCC ARM Embedded](https://developer.arm.com/open-source/gnu-toolchain/gnu-rm).
- Enter to example folder that you want to use and:
    - Compile with ```make```.
    - Clean with ```make clean```.
    - Download to target via OpenOCD with ```make download```.

## Examples

Included examples are:

### ARM Cortex M4 Asembler
 - ```asm_lpc_open```: assembler with LPC Open library
 - ```asm_sapi```: assembler with sAPI library
 
### C language
 - **sAPI library**
    - bare_metal
        - ```adc_dac_01```: ADC and DAC example.
        - bluetooth
            - ```hm10_uart_bridge```: Bluettoth HM10 module AT, tx and rx example.
        - ```cycles_counter_01```: clock cycles counter functions, only work in debug mode. Allows execution time trazability.
        - gpio
            - ```gpio_01_switches_leds```: each switch drives the upper led.
            - ```gpio_02_blinky```: the simply led blinky with a blocking delay.
            - ```gpio_03_blinky_switch```: led blinky with a with a non-blocking delay, to allow you to respond to a switch at the same time.
            - ```gpio_04_led_sequences```: led sequences by using a non-blocking delay.
        - i2c: 
            - magnetometers. In Chinese GY-273 module you can have one of this magnetometers, that have the same pinout but different register map. To difference them see the chip, ignore the board serigraphy.
                - ```hmc5883l```: HMC5883L magnetometer. 
                - ```qmc5883l```: QMC5883L magnetometer.
            - IMUs
                - ```mpu9250```: MPU9250 IMU 9DOF (Gyroscope, Accelerometer and Magnetometer) + Temperature.
        - ```keypad_7segment_01```: Drives a keypad and 7 segment display.
        - ```lcd_01```: Drives a LCD display.
        - pwm
            - ```pwm_01```: PWM applied to LEDs.
            - ```pwm_02_rgb_controller_uart```: RGB LED example.
        - ```rtc_01```: RTC peripheral to have date and time clock.
        - ```sapi_basic_example```: a basic sAPI library example
        - ```servo_01```: angular servomotor PWM control example.
        - ```spi_01_sd_card_fat_filesystem```: ADC logging in a SD/MicroSD Card (SPI connected) by using a FAT File System (ChanFS).
        - temperature_humidity_sensors
            - ```dht11_01```: humidity and temperature sensor.
        - ```tick_01_tick_hook```: periodic tick function (interrupt-based) with periodic callback.
        - uart
            - ```uart_01_echo```: UART echo, it respond the same that you send from PC.
            - ```uart_02_receive_string_blocking```: waits until receive a certain pattern String in a UART or timeout expire (blocking code). Don't save received string.
            - ```uart_03_receive_string```: waits until receive a certain pattern String in a UART or timeout expire (non-blocking code). Don't save received string.
        - ultrasonic_sensors
            - ```hcsr04_01```:  HC-SR04 utrasonic distance sensor.
        - wifi_esp01_esp8266
            - ```01_uart_bridg```: use this to send AT commands directly to ESP01 module.
            - ```02_http_server```: embedded web server to see sensor values.
            - ```03_thingspeak```: send data to thingspeak dashboards.
    - operating_systems
        - coperative (see M.J. Pont's book at https://www.safetty.net/publications/pttes )
            - ```scheduler_01_seos```: first cooperative scheduler
            - ```scheduler_02_seos_background_foreground```: second cooperative scheduler
            - ```seos_pont_2014_01_first_app```: third cooperative scheduler
        - free_rtos
            - dynamic_mem
                - ```freeRTOS_01_blinky```
                - ```freeRTOS_03_ChanFatFS_SPI_SdCard_ADC_log```: ADC logging in a SD/MicroSD Card (SPI connected) by using a FAT File System (ChanFS), freeRTOS and sAPI.
            - static_mem
                - ```freeRTOS_01_blinky```
    - statecharts
        - ```statechart_bare_metal```
 - **LPC Open library**
    - bare_metal
        - ```blinky```
        - ```blinky_input```
        - ```blinky_ram```
        - ```blinky_rit```
        - ```boot```
        - ```i2c```
        - ```lpc_open_basic_example```
        - ```mpu```
        - ```pwm```
    - operating_systems
        - ```freertos_blinky```
    - statecharts
        - ```statechart```
 - ```newlib_printf_scanf```
 - ```without_libs```
 
### C++ language
 - ```cpp_sapi_basic_example```: a C++ basic example with sAPI library.

 
 

## Other examples
 
### Not working yet examples
 - ```adc_fir_dac ```
 - ```asm_conv```
 - ```seos_pont_02_microwave```: SEOS Cooperative O.S. from M.J. Pont (2014), microwave example.
 - ```freeRTOS_02_Queue```: Queue management with freeRTOS and sAPI. 
 - ```freeOSEK_01_blinky```: Blinky led with freeOSEK RTOS.
 - freeRTOS_book: Richard Barry's book examples with FreeRTOS and sAPI:
     - ```example_01```: Creating tasks
     - ```example_02```: Using the task parameter
     - ```example_03```: Experimenting with priorities
     - ```example_04```: Using the Blocked state to create delay
     - ```example_05```: Converting the example tasks to use vTaskDelayUntil()
     - ```example_06```: Combining blocking and non-blocking tasks
     - ```example_07```: Defining an idle task hook function
     - ```example_08```: Changing task priorities
     - ```example_09```: Deleting tasks
     - ```example_10```: Blocking when receiving from a queue
     - ```example_11```: Blocking when sending to a queue or sending structures on a queue
     - ```example_12```: Using a queue set
     - ```example_13```: Creating one-shot and auto-reload timers
     - Dosen't exist: ```example_14```: Using the callback function parameter and the software timer ID
     - ```example_15```: Resetting a software timer
     - ```example_16```: Using a binary semaphore to synchronize a task with an interrupt
     - ```example_17```: Using a counting semaphore to synchronize a task with an interrupt
     - Dosen't exist: ```example_18```: Centralized deferred interrupt processing
     - ```example_19```: Sending and receiving on a queue from within an interrupt
     - ```example_20```: Re-writing vPrintString() to use a semaphore
     - ```example_21```: Re-writing vPrintString() to use a gatekeeper task
     - ```example_22```: Experimenting with event groups
     - The following dosen't exist:
         - ```example_23```: Synchronizing tasks
         - ```example_24```: Using a task notification in place of a semaphore, method 1
         - ```example_25```: Using a task notification in place of a semaphore, method 2
 - LPC4337 LPC Open:
     - ```blinky_osek```
     - ```multicore```
     - ```sd_spi```
     - ```start_m0```
     - ```tcpecho```
     - ```trilat```
     - ```usb_cdc```
     - ```usb_msc_host```
     - ```usb_rom_cdc```

### Deprecated examples
 - ```stdio_01_printf_sprintf```: printf() and other similar standard C libray functions.