# Dual W5100S Loopback Example with STM32

## Overview

This project demonstrates a loopback example using an W5100S-EVB board with extra WIZnet W5100S chip. It allows a single STM32 MCU to interface with two W5100S chips via SPI1 and SPI2, enabling robust networking capabilities.

## Hardware Components

- **['W5100S-EVB'](https://docs.wiznet.io/Product/iEthernet/W5100S/w5100s-evb)** (1 units)
- **[Extra W5100S Chip](https://docs.wiznet.io/Product/iEthernet/W5100S/overview)** (1 units)
- **Connecting Wires**

## Hardware Setup

### 1. Built-in W5100S (SPI Channel 2)

'W5100S-EVB' board comes with W5100S connected through SPI2.

### 2. Additional W5100S (SPI Channel 1)

To add a second W5100S, connect it using SPI1 with the following pin configuration:

| **Signal**  | **STM32 Pin** |
|-------------|---------------|
| SPI1_SCK    | PA5           |
| SPI1_MISO   | PA6           |
| SPI1_MOSI   | PA7           |
| SPI1_CS     | PD2           |
| SPI1_RST    | PD7           |

**Connection Diagram:**


## Software Setup

### 1. Project Structure

- **SPI_DMA/**: Contains the project files and source code.
- **SPI_DMA/debug/**: Stores the compiled `.hex` firmware file.

### 2. Building the Project

1. **Open the Project:**
   - Navigate to the `SPI_DMA` directory.
   - Open the `.project` file using your preferred IDE (e.g., STM32CubeIDE).

2. **Build the Firmware:**
   - Compile the project by selecting the build option in your IDE.
   - Ensure there are no compilation errors.

### 3. Flashing the Firmware

1. **Locate the Firmware:**
   - After a successful build, find the `.hex` file in the `SPI_DMA/debug` directory.

2. **Flash the MCU:**
   - Use the **STM32 Flash Loader Demonstrator** tool to flash the `.hex` file to your STM32 MCU.

   **Download Flash Loader:**
   - [STM32 Flash Loader Demonstrator](https://www.st.com/en/development-tools/flasher-stm32.html)

3. **Flashing Steps:**
   - Install and open the STM32 Flash Loader Demonstrator.
   - Connect your STM32 board to the computer via USB.
   - Select the appropriate `.hex` file.
   - Follow the on-screen instructions to complete the flashing process.

## Usage

Once flashed, the STM32 MCU initializes both W5100S modules, enabling network communication through both Ethernet controllers. This setup is ideal for applications requiring dual Ethernet interfaces, such as network bridging, redundancy, or load balancing.

## Troubleshooting

- **Connection Issues:**
  - Verify all SPI1 connections (PA5, PA6, PA7, PD2, PD7) are secure and correctly mapped.

- **Firmware Flashing Errors:**
  - Make sure that the board has entered boot mode. Boot mode can enter boot mode by clicking Boot 0 switch on the 'W5100S-EVB' board and applying power.
  - Ensure the STM32 Flash Loader Demonstrator is properly installed.
  - Check that the correct `.hex` file is selected.
  - Confirm that the STM32 board is in the correct mode for flashing.

- **Network Communication Problems:**
  - Double-check the network configurations in your code.
  - Ensure both W5100S modules are properly initialized and not conflicting.

## Support

For further assistance, please refer to the project documentation or contact the development team.
