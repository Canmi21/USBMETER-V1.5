## 1.1.4
1. Modified the PPS deception operation logic for smoother handling.
2. Changed the QC/QC3 deception current direction indicator from text to an arrow with temperature, for consistency with other interfaces.
3. Significantly increased the loading speed of the OTA upgrade web interface.
4. Added upload progress indication to the OTA upgrade web page.
5. Optimized the font of voltage, current, and power on the main interface to make them more prominent.
6. Fixed a bug where text overlapped when reading the EMARKER of USB3.0 and higher cables.

## 1.1.5
1. Adjusted font spacing on the main interface.
2. In PD protocol monitoring, if no SRC CAP packet is captured, the main interface will display that PD protocol is used instead of showing empty.
3. Renamed the PD switch setting to PD settings, and removed the SRC CAP query setting.
4. Fixed an issue in PD monitoring where fixed current only got integer values, and adjusted fixed current to requested current (originally PDO current).
5. Fixed a bug where the voltage display sometimes bounced back during sudden voltage drops.
6. Fixed a bug where the CC line direction was misjudged in pass-through mode when connecting to certain chargers.
7. Fixed an ERROR display issue when reading EMARKER in cables longer than 7m.

### IIC Testing Program Update
1. Increased IIC scanning frequency.
2. Added a test to continuously toggle screen pin high and low levels to check for cold solder on the ESP32.
3. Added a button test that outputs the pressed button via serial port.
4. Added the ability to open MOSFETs, allowing for testing the deception button continuity and MOSFET for cold solder under this program.

## 1.1.6
This update is only available as an OTA update package.
1. Added Xiaomi proprietary deception.
2. Added PD3.1 EPR deception.
3. Fixed an intermittent black screen issue during deception under Emarker detection.
4. Optimized PD packet capture and unpacking, increasing the types and amount of information.
5. Optimized PD deception logic, improving compatibility with old PD heads and unconventional chargers.
6. Optimized to allow entering OTA mode using the CC line.
7. Forgot...

## 1.1.7
This update is only available as an OTA update package.
1. Fixed an issue where some generic PD deceptions failed.
2. Fixed an issue where some Xiaomi proprietary deceptions failed.
3. Optimized EPR deception logic.
4. Optimized current direction determination logic.
5. Optimized to no longer read PPS power limit bits during Xiaomi proprietary deception (still reads during monitoring).
6. Optimized main interface protocol determination.
7. Fixed a display misalignment issue with currents over 10A.
8. Improved the accuracy and consistency of ADC readings.
9. Added support for deceiving more Xiaomi proprietary heads.
10. Added the ability to read EPR cables with Emarker (added in the previous version).
Note: The previous version's optimization for entering OTA mode using the CC line may cause modded PD heads using AC line to enter OTA with infinite screen flashing. If flashing occurs, hold the + key while pressing the corresponding deception button.

## 1.1.8
1. Fixed an issue where deceiving Apple USB-C and a few other heads failed.
2. Added Thunderbolt 3/4 to Emarker reading.
3. Slightly adjusted button logic, short press reduced to within 300ms, hold trigger time reduced to 1s or more.
4. Improved the accuracy and consistency of ADC readings.
5. Fixed a bug where the screen couldn't be manually turned off after enabling smart backlight.
6. Added EX message unpacking.
7. Added identifiers for self-generated packets and CRC packets in unpacking.
8. The firmware no longer differentiates between screen types, hold the confirmation button for 8s or more on the main interface to switch screen types.
9. Truly added the ability to read EPR cables with Emarker this time.
Note: If encountering a flashing screen when entering OTA, hold the + key while pressing the corresponding deception button. It is recommended to use OTA upgrades as TTL upgrades will result in loss of all stored data, including registration information.

## 1.1.9
1. Changed the units of electrical power statistics to Wh and mAh, aligning with conventional statistical habits.
2. Minor adjustment to the position of power metrics on the main interface.
3. Added a new setting for single-point current calibration, supporting calibration for current values from 1~6A (Calibration method: Connect a standard ammeter in series at the meter's input, with the meter using a male input and the output connected to a stable resistive load. Set the ammeter's reading as the standard current value, use +/- keys to adjust the digits, and the confirm key to move to the next digit. Press confirm on the last digit to enter the save interface. Select 'save' to complete calibration, 'do not save' to abandon changes, and 'restore defaults' to reset to default values).
4. Lowered the minimum brightness threshold.
5. In pass-through mode, holding the + key forces a CC pull-down, facilitating the deception of modded A-port protocols (can plug in the cable before holding the + key and the corresponding deception button, instead of having to hold the deception button while plugging in).
6. Due to a conflict between the + key and OTA upgrade mode, changed OTA upgrade mode entry to holding the - key while powering on.
7. Holding the confirm button to return to the main interface from QC deception no longer clears the deception protocol.
8. PD deception mode can no longer access QC deception interface.
9. After flipping the screen, the hold operations for the +/- keys no longer reverse.
10. Fixed a bug with PD3.1 reading and deception failure.
11. Fixed an issue with EPR Request packet parsing error in EPR.

## 1.2.0
1. Removed battery voltage setting.
2. Removed PD monitoring setting.
3. Added a new setting for deception settings, allowing users to choose deception options after powering on (Usage logic: Select FIX to prioritize FIX deception, automatically seeking the nearest voltage setting to the set FIX deception voltage; select PPS to prioritize PPS deception, and if the set voltage/current values exceed the packet, it will automatically deceive using the nearest value, switching to FIX deception if no PPS slot is available).
4. Added a sampling filter mode selection to address issues with high-frequency PWM signals.
5. Changed the calculation of mAh in power statistics from battery voltage and Wh to current integration, automatically performing 1/2/4 times integration based on voltage, aligning with current mainstream mobile phone charging schemes.
6. Slightly extended the data update interval to prevent data from fluctuating too quickly for reading.
7. Modifications to PPS deception allow long-press to quickly adjust voltage/current.
8. Added a buffer waiting and detection interface when entering QC deception to prevent quick-hand operation failures.
9. Fixed an issue where the forced CC pull-down operation via the + key became ineffective after flipping the screen.
10. Interface color scheme refreshed, overall colors unified, and PPS and QC3 deception interfaces redrawn.
11. After registration, the version information interface displays the device's SN and registration information.
(Note: In version 1.1.9, the method to enter OTA update changed to holding the - key on power-up; it is recommended to use OTA upgrade, as TTL upgrade will lose all stored data including registration information).

## 1.2.1 Emergency Bug Fix
1. Fixed an issue where initial registration verification failed.
2. Fixed an issue where entering QC deception for the second time displayed as unsupported.
3. Enabled internal pull-up for buttons to prevent cold solder from causing the interface to freeze.

## 1.2.2
1. Changed to a new default color scheme, with three colors available for selection in settings.
2. Re-entering after self-consumption zero calibration now clears zero calibration data.
3. Fixed some minor bugs.

## 1.2.3
1. Registration exempted.
(Note: "Registration" has been removed in version 1.2.3).
