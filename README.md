# Bare-Metal AVR Protocol Implementations

A collection of register-level firmware projects on the ATmega328P (Arduino Uno), implementing the core embedded communication protocols — UART, I2C, and SPI — entirely from scratch using direct register manipulation, without high-level Arduino libraries (`Serial`, `Wire`, `SPI`).

Built to deepen low-level understanding of microcontroller peripherals: clock configuration, interrupt handling, protocol timing compliance, and hardware communication state machines.

## Projects

| Project | Protocol | Description | Documentation |
|---|---|---|---|
| [`uart-interrupt-counter`](./uart-interrupt-counter) | UART + External Interrupt | Interrupt-driven button counter transmitting live counts over serial | [Link] |
| [`i2c-mpu6050`](./i2c-mpu6050) | I2C (TWI) | Reads live accelerometer data from an MPU6050 sensor | [Link] |
| [`avr-spi-74hc595`](./avr-spi-74hc595) | SPI + Logic Analyzer | High-speed SPI driving a 74HC595 shift register as a synchronous 8-bit binary counter, verified via digital logic tracing | [Link] |

## Why Bare-Metal?

Each project avoids high-level Arduino abstractions in favor of direct register access (`DDRx`, `PORTx`, `UCSR0x`, `TWCR`, `SPCR`, etc.), the same level at which production embedded firmware is typically written. This demonstrates understanding of:
- Microcontroller peripheral configuration and clock prescaling at the hardware level
- Protocol-specific state machines (START/STOP conditions, ACK/NACK, SPI Mode 0 transmission)
- Hardware verification using digital logic analyzer trace logging (.VCD files)
- Reading and applying microcontroller and IC datasheet register descriptions directly

## Toolchain & Verification
- **Compiler:** AVR-GCC / `avrdude`
- **Simulation Environments:** Wokwi & TinkerCAD Circuits (Portable to physical ATmega328P/Arduino Uno hardware)
- **Debugging & Verification:** PulseView / Waveform VCD Tracing

## Author
Asad Sajid — Final Year Electronics Engineering, NED University of Engineering & Technology
