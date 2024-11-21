# SpeedyBee F405 V4 Firmware Change

This repository provides a step-by-step guide for changing the firmware on the SpeedyBee F405 V4 flight controller. Specifically, it demonstrates how to flash iNav firmware using a USB connection and configure it to work with Mission Planner. The process utilizes DFU mode and the STM32CubeProgrammer, providing a straightforward method to explore different firmware options for your flight controller.

---

## **Why Change Firmware?**
1. **Experimentation**: Explore the capabilities of iNav and compare them with other firmware like Betaflight or ArduPilot.
2. **Customization**: Unlock features like GPS navigation and waypoint missions with iNav.
3. **Flexibility**: Use Mission Planner for advanced telemetry and mission planning.

---

## **Required Tools and Resources**
- **Hardware**:
  - SpeedyBee F405 V4 Flight Controller.
  - USB-C Cable.
- **Software**:
  - [STM32CubeProgrammer](https://www.st.com/en/development-tools/stm32cubeprog.html) (for flashing firmware).
  - [Mission Planner](https://ardupilot.org/planner/docs/mission-planner-installation.html) (for configuration and testing).
  - iNav Configurator (for iNav setup and configuration).

- **Firmware**:
  - [iNav Firmware (SpeedyBee F405 V4)](https://github.com/iNavFlight/inav/releases).
  - Hex file provided in this repository.

---

## **Step-by-Step Guide**

### 1. **Enter DFU Mode**
- Connect the SpeedyBee F405 V4 to your computer using a USB-C cable.
- Hold down the **Boot** button on the flight controller and plug in the USB cable.
- Verify that the board is in DFU mode by checking the device manager (Windows) or `lsusb` (Linux).

### 2. **Download and Install STM32CubeProgrammer**
- Download STM32CubeProgrammer from [STMicroelectronics](https://www.st.com/en/development-tools/stm32cubeprog.html).
- Install the software on your computer.

### 3. **Download the Firmware**
- Obtain the latest iNav firmware for the SpeedyBee F405 V4 from [this link](https://github.com/iNavFlight/inav/releases).
- Ensure you download the correct `.hex` file for your flight controller.

### 4. **Flash the Firmware**
1. Open STM32CubeProgrammer.
2. Select the **DFU** connection type.
3. Click **Connect**.
4. Erase the chip:
   - Go to the **Erasing & Programming** section and choose **Full Chip Erase**.
5. Flash the firmware:
   - Click **Add File** and select the `.hex` file.
   - Click **Start Programming** to write the firmware.

### 5. **Verify the Flash**
- After the programming is complete, power-cycle the flight controller.
- Open Mission Planner to confirm the board is running iNav.

### 6. **Set Up iNav**
- Use the [iNav Configurator](https://github.com/iNavFlight/inav-configurator/releases) to configure your flight controller:
  - Calibrate accelerometer, gyroscope, and magnetometer.
  - Configure GPS and flight modes.
  - Test motor outputs and assign UART ports.

---

## **Additional Notes**
- **Switching Back to Betaflight or Other Firmware**:
  - Follow the same steps, but use the appropriate firmware file for Betaflight or ArduPilot.
- **Recovering from Failed Flashes**:
  - If the board does not boot after flashing, re-enter DFU mode and repeat the process.

---

## **Useful Links**
- [STM32CubeProgrammer Documentation](https://www.st.com/resource/en/user_manual/dm00403500-stm32cubeprogrammer-stmicroelectronics.pdf)
- [iNav Official Documentation](https://inavflight.com/)
- [Mission Planner Documentation](https://ardupilot.org/planner/)
