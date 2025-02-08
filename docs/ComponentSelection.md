# **Component Selection**

## **Major Components**
For the motor drive subsystem, the main components will be the motors and the motor driver. We also need to think about the system's power source as well as regulating that power so our components do not burn. This system will be using a PIC Microcontroller from Microchip to communicate with the motor driver through Serial Peripheral Interface(SPI) or Inter-Integrated Circuit(I2C).

### **Brushed DC Motor**
| **Selected Product**     | **Rationale for Optimal Solution**                                              |
|------------------|-------|
|  |  |
#### Benchmarked Products
| Product          | Price | Links       | Pros                           | Cons                         |
|------------------|-------|-----------------|--------------------------------|------------------------------|
| SE18K1ETY ![BDC Motor 1](images/components/SE18K1ETY.jpg) | $9.28 | [Digikey](https://www.digikey.com/en/products/detail/nmb-technologies-corporation/SE18K1ETY/6021449) / [Datasheet](https://mm.digikey.com/Volume0/opasdata/d220001/medias/docus/734/SE18K.pdf) | -   <br> - <br> -  | -   <br> - <br> - |
| HC385G-302 ![BDC Motor 2](images/components/HC385G-302.jpg) | $7.01 | [Digikey](http://digikey.com/en/products/detail/johnson-motor/HC385G-302/12723725) / [Datasheet](https://www.johnsonelectric.com/pub/media/datasheetdownloadpdf/pdf/HC385G_302_metric_3__0.pdf) | -   <br> - <br> - | -   <br> - <br> - |
| ROB-11696 ![BDC Motor 3](images/components/ROB-11696.jpg) | $2.10 | [Digikey](https://www.digikey.com/en/products/detail/sparkfun-electronics/ROB-11696/6163657) / [Datasheet](https://mm.digikey.com/Volume0/opasdata/d220001/medias/docus/951/ROB-11696_Web.pdf) | -   <br> - <br> - | -   <br> - <br> - |


### **Motor Driver**
| **Selected Product**     | **Rationale for Optimal Solution**                                              |
|------------------|-------|
|  |  |
#### Benchmarked Products
| Product          | Price | Links       | Pros                           | Cons                         |
|------------------|-------|-----------------|--------------------------------|------------------------------|
| NCV7719DQAR2G ![Motor Driver 1](images/components/NCV7719DQAR2G.jpg) | $5.99 | [Digikey](https://www.digikey.com/en/products/detail/onsemi/NCV7719DQAR2G/12529076) / [Datasheet](https://www.onsemi.com/download/data-sheet/pdf/ncv7719-d.pdf) | - <br> - <br> - | - <br> - <br> - |
| DRV8830DGQR ![Motor Driver 2](images/components/DRV8830DGQR.jpg) | $2.09 | [Digikey](https://www.digikey.com/en/products/detail/texas-instruments/DRV8830DGQR/2520903) / [Datasheet](https://www.ti.com/lit/ds/symlink/drv8830.pdf?HQS=dis-dk-null-digikeymode-dsf-pf-null-wwe&ts=1738989981632&ref_url=https%253A%252F%252Fwww.ti.com%252Fgeneral%252Fdocs%252Fsuppproductinfo.tsp%253FdistId%253D10%2526gotoUrl%253Dhttps%253A%252F%252Fwww.ti.com%252Flit%252Fgpn%252Fdrv8830) | - <br> - <br> - | - <br> - <br> - |
| NCV7708FDWR2G ![Motor Driver 3](images/components/NCV7708FDWR2G.jpg) | $5.83 | [Digikey](https://www.digikey.com/en/products/detail/onsemi/NCV7708FDWR2G/9829237) / [Datasheet](https://www.onsemi.com/pdf/datasheet/ncv7708f-d.pdf) | - <br> - <br> - | - <br> - <br> - |


### **Voltage Regulator**
| **Selected Product**     | **Rationale for Optimal Solution**                                              |
|------------------|-------|
|  |  |
#### Benchmarked Products
| Product          | Price | Links       | Pros                           | Cons                         |
|------------------|-------|-----------------|--------------------------------|------------------------------|
| LM2674MX-3.3/NOPB ![Voltage Regulator 1](images/components/LM2674MX-3.3.jpg) | $3.37 | [Digikey](https://www.digikey.com/en/products/detail/texas-instruments/LM2674MX-3-3-NOPB/366902) / [Datasheet](https://www.ti.com/lit/ds/symlink/lm2674.pdf?HQS=dis-dk-null-digikeymode-dsf-pf-null-wwe&ts=1738969322841&ref_url=http%253A%252F%252Fwww.wjs2ic.com%252F) |  - <br> - <br> - |  - <br> - <br> - |
| MIC4680-3.3YM ![Voltage Regulator 2](images/components/MIC4680-3.3YM.jpg)  | $2.96 | [Digikey](https://www.digikey.com/en/products/detail/microchip-technology/MIC4680-3-3YM/771689) / [Datasheet](https://ww1.microchip.com/downloads/en/DeviceDoc/mic4680.pdf) |  - <br> - <br> - |  - <br> - <br> - |
| ADPL44002AUJZ-3.3-R7 ![Voltage Regulator 3](images/components/ADPL44002AUJZ-3.3-R7.jpg) | $1.51 | [Digikey](https://www.digikey.com/en/products/detail/analog-devices-inc/ADPL44002AUJZ-3-3-R7/25803461) / [Datasheet](https://www.mouser.com/datasheet/2/609/1/adpl44002-3535120.pdf) | - <br> - <br> -  |  - <br> - <br> - |


### **Power Supply**
| **Selected Product**     | **Rationale for Optimal Solution**                                              |
|------------------|-------|
|  |  |
#### Benchmarked Products
| Product          | Price | Links       | Pros                           | Cons                         |
|------------------|-------|-----------------|--------------------------------|------------------------------|
|  |  | [Digikey]() / [Datasheet]() |  - <br> - <br> - |  - <br> - <br> - |
|  |  | [Digikey]() / [Datasheet]() |  - <br> - <br> - |  - <br> - <br> - |
|  |  | [Digikey]() / [Datasheet]() |  - <br> - <br> - |  - <br> - <br> - |

### **Microcontroller**
| ESP Info                                      | Answer |
| --------------------------------------------- | ------ | 
| Model                                         | ?      | 
| Product Page URL                              | ?      |
| Datasheet URL(s)                              | ?      |
| Application Notes URL(s)                      | ?      |
| Vendor link                                   | ?      |
| Code Examples                                 | ?      |
| External Resources URL(s)                     | ?      |
| Unit cost                                     | ?      |
| Absolute Maximum Current for entire IC        | ?      |
| Supply Voltage Range                          | ?      |
| Absolute Maximum current <br> (for entire IC) | ?      |
| Maximum GPIO current <br> (per pin)           | ?      |
| Supports External Interrupts?                 | ?      |
| Required Programming Hardware, Cost, URL      | ?      |
| Works with MPLabX?                            | ?      |
| Works with Microchip Code Configurator?       | ?      |


| Module | # Available | Needed | Associated Pins (or * for any) |
| ---------- | ----------- | ------ | ------------------------------ |
| GPIO       | ?           | ?      | ?                              |
| ADC        | ?           | ?      | ?                              |
| UART       | ?           | ?      | ?                              |
| SPI        | ?           | ?      | ?                              |
| I2C        | ?           | ?      | ?                              |
| PWM        | ?           | ?      | ?                              |
| ICSP       | ?           | 1      | ?                              |
| ...        | ...         | ...    | ...                            |


