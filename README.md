# Adc-driver
        ADC Driver for AVR ATmega32 written in Embedded C
# ADC Driver for AVR ATmega32

A simple and reusable ADC (Analog-to-Digital Converter) driver for the AVR ATmega32 microcontroller.

---

## Author

**Youssef Tamer**

GitHub: https://github.com/Yousseftamer883-droid

---

## Project Overview

This project implements a complete ADC driver for the ATmega32 microcontroller.

The driver allows the user to initialize the ADC peripheral, configure the reference voltage and clock prescaler, start ADC conversions, check conversion status, and read digital conversion results.

The driver is written in Embedded C following a modular architecture suitable for embedded systems projects.

---

## Features

- ADC Initialization
- ADC Deinitialization
- Select ADC Channel
- Start ADC Conversion
- Read ADC Result
- Blocking ADC Read
- Conversion Status Check
- Configurable Voltage Reference
- Configurable ADC Prescaler
- Modular Driver Design

---

## Folder Structure

```
Project
│
├── HAL/
├── MCL/
│   └── ADC/
│       ├── adc.c
│       ├── adc_interface.h
│       ├── adc_registers.h
│
├── Service/
│       ├── STD_Types.h
│       └── Bit_Math.h
│
├── src/
├── build/
├── Makefile
└── README.md
```

---

## Driver APIs

### ADC_Init()

Initializes the ADC peripheral.

---

### ADC_DeInit()

Disables the ADC module.

---

### ADC_StartConversion()

Selects an ADC channel and starts conversion.

---

### ADC_IsConversionComplete()

Checks whether conversion is finished.

Returns:

- ADC_CONVERSION_DONE
- ADC_CONVERSION_BUSY

---

### ADC_ReadResult()

Reads the 10-bit ADC conversion result.

---

### ADC_ReadChannelBlocking()

Starts conversion and waits until completion before returning the ADC value.

---

## Example

```c
ADC_ConfigType config;

config.uint8ReferenceVoltage = ADC_AVCC;
config.uint8Prescaler = ADC_PRESCALER_128;

ADC_Init(&config);

uint16_h value;

ADC_ReadChannelBlocking(0, &value);
```

---

## Build

Compile using the provided Makefile.

```
make
```

---

## Requirements

- AVR GCC
- Make
- ATmega32
- VS Code (optional)

---

## Driver Workflow

Initialize ADC

↓

Configure Reference Voltage

↓

Configure Prescaler

↓

Select Channel

↓

Start Conversion

↓

Wait Until Finished

↓

Read Result

---

## Future Improvements

- ADC Interrupt Mode
- Auto Trigger Support
- Free Running Mode
- Callback Functions
- Noise Reduction Mode

---

## License

This project was developed for educational purposes during Embedded Systems Summer Training.
