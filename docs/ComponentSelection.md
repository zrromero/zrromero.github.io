# **Component Selection**

## **Major Components**
For the motor drive subsystem, the main components will be the motors and the motor driver. We also need to think about the system's power source as well as regulating that power so our components do not burn. This system will be using a PIC Microcontroller from Microchip to communicate with the motor driver through Serial Peripheral Interface(SPI) or Inter-Integrated Circuit(I2C).

### **Brushed DC Motor**
| **Selected Product**     | **Rationale for Optimal Solution**                                              |
|------------------|-------|
| HC385G-302 <br> ![BDC Motor 2](images/components/HC385G-302.jpg){: style="max-width: 250px; max-height: 250px;" } <br> Price: $7.01 <br> [Digikey](http://digikey.com/en/products/detail/johnson-motor/HC385G-302/12723725) / [Datasheet](https://www.johnsonelectric.com/pub/media/datasheetdownloadpdf/pdf/HC385G_302_metric_3__0.pdf) |  |

#### Benchmarked Products
| Product          | Price | Links       | Pros                           | Cons                         |
|--|-------|-----------------|--------------------------------|------------------------------|
| SE18K1ETY <br> ![BDC Motor 1](images/components/SE18K1ETY.jpg){: style="max-width: 250px; max-height: 250px;" } | $9.28 | [Digikey](https://www.digikey.com/en/products/detail/nmb-technologies-corporation/SE18K1ETY/6021449) / [Datasheet](https://mm.digikey.com/Volume0/opasdata/d220001/medias/docus/734/SE18K.pdf) | - Compact Size <br> - High Efficiency <br> - Durable         | - Limited Torque <br> - Relatively Expensive <br> - Requires Proper Heat Dissipation      |
| HC385G-302 <br> ![BDC Motor 2](images/components/HC385G-302.jpg){: style="max-width: 250px; max-height: 250px;" } | $7.01 | [Digikey](http://digikey.com/en/products/detail/johnson-motor/HC385G-302/12723725) / [Datasheet](https://www.johnsonelectric.com/pub/media/datasheetdownloadpdf/pdf/HC385G_302_metric_3__0.pdf) | - Versatile <br> - Reliable Performance <br> - Affordable    | - Size <br> - Lower Efficiency <br> - Not as Durable                                      |
| ROB-11696 <br> ![BDC Motor 3](images/components/ROB-11696.jpg){: style="max-width: 250px; max-height: 250px;" } | $2.10 | [Digikey](https://www.digikey.com/en/products/detail/sparkfun-electronics/ROB-11696/6163657) / [Datasheet](https://mm.digikey.com/Volume0/opasdata/d220001/medias/docus/951/ROB-11696_Web.pdf) | - Small and Lightweight <br> - Easy Integration <br> - Low Cost | - Low Torque <br> - Not Highly Durable <br> - Limited Speed Range                         |


### **Motor Driver**
| **Selected Product**     | **Rationale for Optimal Solution**                                              |
|------------------|-------|
| DRV8830DGQR <br> ![Motor Driver 2](images/components/DRV8830DGQR.jpg){: style="max-width: 250px; max-height: 250px;" } <br> Price: $2.09 <br> [Digikey](https://www.digikey.com/en/products/detail/texas-instruments/DRV8830DGQR/2520903) / [Datasheet](https://www.ti.com/lit/ds/symlink/drv8830.pdf?HQS=dis-dk-null-digikeymode-dsf-pf-null-wwe&ts=1738989981632&ref_url=https%253A%252F%252Fwww.ti.com%252Fgeneral%252Fdocs%252Fsuppproductinfo.tsp%253FdistId%253D10%2526gotoUrl%253Dhttps%253A%252F%252Fwww.ti.com%252Flit%252Fgpn%252Fdrv8830) |  |

#### Benchmarked Products
| Product          | Price | Links       | Pros                           | Cons                         |
|--|-------|-----------------|--------------------------------|------------------------------|
| NCV7719DQAR2G <br> ![Motor Driver 1](images/components/NCV7719DQAR2G.jpg){: style="max-width: 250px; max-height: 250px;" } | $5.99 | [Digikey](https://www.digikey.com/en/products/detail/onsemi/NCV7719DQAR2G/12529076) / [Datasheet](https://www.onsemi.com/download/data-sheet/pdf/ncv7719-d.pdf) | - Versatile Voltage Range <br> - Integrated Protection Features <br> - Low Power Consumption              | - Requires External Heat Sink for High Loads <br> - Limited Current Handling <br> - Can Be Sensitive to Voltage Spikes      |
| DRV8830DGQR <br> ![Motor Driver 2](images/components/DRV8830DGQR.jpg){: style="max-width: 250px; max-height: 250px;" } | $2.09 | [Digikey](https://www.digikey.com/en/products/detail/texas-instruments/DRV8830DGQR/2520903) / [Datasheet](https://www.ti.com/lit/ds/symlink/drv8830.pdf?HQS=dis-dk-null-digikeymode-dsf-pf-null-wwe&ts=1738989981632&ref_url=https%253A%252F%252Fwww.ti.com%252Fgeneral%252Fdocs%252Fsuppproductinfo.tsp%253FdistId%253D10%2526gotoUrl%253Dhttps%253A%252F%252Fwww.ti.com%252Flit%252Fgpn%252Fdrv8830) | - Small Package Size <br> - Low Power Consumption <br> - Integrated Fault Protection                     | - Limited Output Current <br> - Requires External Decoupling Capacitors <br> - May Overheat under High Loads               |
| NCV7708FDWR2G <br> ![Motor Driver 3](images/components/NCV7708FDWR2G.jpg){: style="max-width: 250px; max-height: 250px;" } | $5.83 | [Digikey](https://www.digikey.com/en/products/detail/onsemi/NCV7708FDWR2G/9829237) / [Datasheet](https://www.onsemi.com/pdf/datasheet/ncv7708f-d.pdf) | - High Efficiency <br> - Integrated Protection Features <br> - Robust for Motor Control Applications       | - Requires External Components for Full Operation <br> - Can be Sensitive to Temperature <br> - Limited to Specific Loads   |


### **Voltage Regulator**
| **Selected Product**     | **Rationale for Optimal Solution**                                              |
|------------------|-------|
|  MIC4680-3.3YM <br> ![Voltage Regulator 2](images/components/MIC4680-3.3YM.jpg){: style="max-width: 250px; max-height: 250px;" } <br> Price: $2.96 <br> [Digikey](https://www.digikey.com/en/products/detail/microchip-technology/MIC4680-3-3YM/771689) / [Datasheet](https://ww1.microchip.com/downloads/en/DeviceDoc/mic4680.pdf) |  |

#### Benchmarked Products
| Product          | Price | Links       | Pros                           | Cons                         |
|--|-------|-----------------|--------------------------------|------------------------------|
| LM2674MX-3.3/NOPB <br> ![Voltage Regulator 1](images/components/LM2674MX-3.3.jpg){: style="max-width: 250px; max-height: 250px;" } | $3.37 | [Digikey](https://www.digikey.com/en/products/detail/texas-instruments/LM2674MX-3-3-NOPB/366902) / [Datasheet](https://www.ti.com/lit/ds/symlink/lm2674.pdf?HQS=dis-dk-null-digikeymode-dsf-pf-null-wwe&ts=1738969322841&ref_url=http%253A%252F%252Fwww.wjs2ic.com%252F){: style="max-width: 250px; max-height: 250px;" } | - High Efficiency <br> - Compact Size <br> - Reliable Voltage Regulation | - Requires External Components for Full Operation <br> - Limited Output Current <br> - May Require Heat Sinking |
| MIC4680-3.3YM <br> ![Voltage Regulator 2](images/components/MIC4680-3.3YM.jpg){: style="max-width: 250px; max-height: 250px;" }  | $2.96 | [Digikey](https://www.digikey.com/en/products/detail/microchip-technology/MIC4680-3-3YM/771689) / [Datasheet](https://ww1.microchip.com/downloads/en/DeviceDoc/mic4680.pdf) | - Low Dropout Voltage <br> - Wide Input Voltage Range <br> - Compact Design    | - Lower Output Current Rating <br> - May Require External Capacitors <br> - Performance Affected by Load Variation |
| ADPL44002AUJZ-3.3-R7 <br> ![Voltage Regulator 3](images/components/ADPL44002AUJZ-3.3-R7.jpg){: style="max-width: 250px; max-height: 250px;" } | $1.51 | [Digikey](https://www.digikey.com/en/products/detail/analog-devices-inc/ADPL44002AUJZ-3-3-R7/25803461) / [Datasheet](https://www.mouser.com/datasheet/2/609/1/adpl44002-3535120.pdf) | - High Precision <br> - Low Power Consumption <br> - Small Package | - Limited Output Current <br> - May Need Additional Filtering <br> - Can Be Sensitive to Temperature Changes |


### **Power Supply**
| **Selected Product**     | **Rationale for Optimal Solution**                                              |
|------------------|-------|
|  |  |

#### Benchmarked Products
| Product          | Price | Links       | Pros                           | Cons                         |
|--|-------|-----------------|--------------------------------|------------------------------|
|  <br> ![Power Supply 1](images/components/.jpg){: style="max-width: 250px; max-height: 250px;" } |  | [Digikey]() / [Datasheet]() |  - <br> - <br> - |  - <br> - <br> - |
|  <br> ![Power Supply 1](images/components/.jpg){: style="max-width: 250px; max-height: 250px;" } |  | [Digikey]() / [Datasheet]() |  - <br> - <br> - |  - <br> - <br> - |
|  <br> ![Power Supply 1](images/components/.jpg){: style="max-width: 250px; max-height: 250px;" } |  | [Digikey]() / [Datasheet]() |  - <br> - <br> - |  - <br> - <br> - |

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


###### This Page Uses Some AI generated Content
