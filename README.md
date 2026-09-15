# ECE 528/L - Robotics and Embedded Systems Lab
**CSU Northridge**

**Department of Electrical and Computer Engineering**

## GPIO Lab
The GPIO lab interfaces with the following:

* User buttons and LEDs of the TI MSP432 LaunchPad
* PMOD SWT (4 Slide Switches) - [Product Link](https://digilent.com/reference/pmod/pmodswt/start)
* PMOD 8LD (8 LEDs) - [Product Link](https://digilent.com/shop/pmod-8ld-eight-high-brightness-leds/)

## LED Patterns

The `LED_Controller` function selects a pattern based on the PMOD SWT status.

* **All switches off** - `LED_Pattern_1`, output set by the two user buttons
* **SWT1** - `LED_Pattern_2`, 8-bit binary up counter, 100 ms
* **SWT2** - `LED_Pattern_3`, 8-bit binary down counter, 100 ms
* **SWT1 + SWT2** - `Johnson_Counter`, 8-bit Johnson (twisted ring) counter, 200 ms
* **SWT3** - `LED_Pattern_4`, ring counter shifting left, 200 ms
* **SWT4** - `LED_Pattern_5`, ring counter shifting right, 200 ms

## Screenshots

Taken during a CCS debug session by expanding the port in the **Registers** window and
clicking **Step Over** until after the matching init function had been called.

### Port 1 - after LED1_Init (P1DIR)
![Port 1](screenshots/ece528L_lab0_gpio_port1.png)

### Port 2 - after LED2_Init (P2DIR, P2DS)
![Port 2](screenshots/ece528L_lab0_gpio_port2.png)

### Port 9 - after PMOD_8LD_Init (P9DIR)
![Port 9](screenshots/ece528L_lab0_gpio_port9.png)

### Port 10 - after PMOD_SWT_Init (P10DIR, unchanged)
![Port 10](screenshots/ece528L_lab0_gpio_port10.png)