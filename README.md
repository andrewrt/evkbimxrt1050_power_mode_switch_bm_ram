# evkbimxrt1050_power_mode_switch_bm_ram

Copy of the evkbimxrt1050_power_mode_switch_bm demo, removing FLASH and UART utilization - putting device directly to SNVS sleep mode. 

Steps to recreate:
* MCUXpresso: Import RT1052 SDK example: evkbimxrt1050_power_mode_switch_bm, removing flash section in memory layout & linking to Internal RAM
* In code: comment out PRINTF and scan references, and hard set power mode to SNVS: 
  ```c
   s_targetPowerMode = LPM_PowerModeSNVS
  ```
* Comment out Debug Console / UART config (not using UART).
* Run, then disconnect debugger cable to ensure JTAG pullups not affecting current.


