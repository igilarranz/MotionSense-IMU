# MotionSense IMU

MotionSense IMU is a small 2-layer PCB I designed around the ST LSM6DSM accelerometer/gyroscope.

The board takes 5 V from USB-C, regulates it to 3.3 V, and breaks out the IMU's I2C signals and interrupt pin through a 5-pin header.

![3D render](docs/images/motionSense_3d.png)

## Hardware

- LSM6DSM 6-axis IMU
- AP2112K-3.3 LDO
- USB-C 5 V input
- 4.7 kΩ pull-ups on SDA and SCL
- Decoupling capacitors for the regulator and IMU
- 5-pin header:
  - 3V3
  - GND
  - SDA
  - SCL
  - INT1

Board size: about 35 mm × 27 mm.

## Design

I made the schematic and PCB in KiCad.

For placement and routing, I experimented with Quilter and Freerouting, then brought the board back into KiCad for cleanup and DRC.

The final board passes KiCad DRC with:

- 0 violations
- 0 unconnected items

I also generated and checked the Gerber and drill files in GerbView.

## Pinout

| Pin | Signal |
|---|---|
| 1 | 3V3 |
| 2 | GND |
| 3 | SDA |
| 4 | SCL |
| 5 | INT1 |

## Files

- `hardware/` — KiCad project files and BOM
- `fabrication/` — Gerber + drill ZIP
- `docs/images/` — board screenshots/renders

## Current Status

The PCB design is complete and fabrication files are ready.

I have not assembled or tested the physical board yet, so the next step is to order it and do hardware bring-up.

## Next Steps

- Order the PCB
- Assemble the board
- Check 5 V input and 3.3 V output
- Connect a microcontroller over I2C
- Read accelerometer and gyroscope data
- Test the INT1 pin
- Document any changes needed for Rev 2

## Preview

![Gerber preview](docs/images/gerber_preview.png)
