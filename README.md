# MotorCAN
CANBus based FOC motor driver board designed for drone gimbal motors for node-based control, designed in KiCad.

Features:
  - STM32G431 processor core for SimpleFOC software and CAN communication
  - 3.3V CAN communication for easy logic level support
  - Runs on 20-26V DC
  - Integrated magnetic absolute encoder (MT6816CT)
  - Handles up to ~3A of motor current

This driver is designed to be a fully integrated solution that mounts to the back of a gimbal motor with a diametrically magnetized magnet. For that reason, it includes an absoulute magnetic encoder and leverages the current sensing capabilities of the DRV8316C driver to maintain a continous measurement of the position of the rotor of the motor and its magnetic field. Then, the STM32 running SimpleFOC calculates the exact currents on each phase needed to create a magnetic torque on the motor that is 90 degrees from the magnetic field and therefore gives the greatest overall control of the motor. This chip also has a 3.3V CAN chip so it can link up to a simple 4 wire network of muliple of these boards for applications like camera gimbals.

Credits:
SimpleFOC: https://github.com/simplefoc
KiCad: https://www.kicad.org
