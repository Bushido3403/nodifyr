```mermaid
flowchart TD
  %% Sources
  USB5V[USB-C 5V (VBUS)] --> DUSB[Ideal Diode (USB path)]
  VBAT[Li-Po Cell (VBAT)] --> CHG[Battery Charger]
  CHG --> DBAT[Ideal Diode (Battery path)]

  %% OR-ing into system rail
  DUSB --> SYS[(SYS Rail)]
  DBAT --> SYS

  %% Regulation
  SYS --> BUCK[3V3 Buck Regulator]
  BUCK --> V3V3[(3V3 Rail)]

  %% Loads
  V3V3 --> MCU[ESP32-S3 Module]
  V3V3 --> PERIPH["Peripherals & Headers"]
  V3V3 --> ACC[Accessories]
```