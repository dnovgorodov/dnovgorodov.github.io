---
title: Component Selection
---

## Overview
During my component selection process, I considered many factors: cost, use, effectiveness, accuracy, etc. For the load cell (or weight sensor), I chose the SparkFun 50kg Load Cell because of its impressive weight-detection capacity, accurate detection through ADC signaling, and relatively low cost. For the 5V voltage regulator, I chose the LM7805T due to my familiarity with it, ease-of-use, and once again, low cost. For the op-amp, I had originally chosen the AD620ANZ due to its accuracy and low offset voltage, but eventually decided to do with the INA333 due to its lower quiescent current and lower cost.

## Component 1 — Load Cell (Weight Sensor)

| **Solution** | **Photo** | **Link & Cost** | **Pros** | **Cons** |
|---------------|------------|------------------|-----------|-----------|
| **SparkFun Load Cell – 50 kg (Generic)** | ![Generic](https://www.sparkfun.com/media/catalog/product/cache/a793f13fd3d678cea13d28206895ba0c/1/0/10245-01a.jpg) | [SparkFun Load Cell – 50 kg (Generic)](https://www.sparkfun.com/load-sensor-50kg-generic.html) - $6.25 | Accurate (±0.02%), easy to mount, widely supported | Off-center loads reduce accuracy |
| **50kg Strain Gauge** | ![Strain Gauge](https://i.ebayimg.com/images/g/x~oAAOSw79Vm86qD/s-l1600.webp) | [Phidgets Micro Load Cell (0–50 kg)](https://www.ebay.com/itm/286077381781) - $6.99 | High range, compact, reliable industrial supplier | Seems to be a lot of wiring |
| **Velleman WPSE471 Load Cell + ADC** | ![Velleman Load Cell](https://mm.digikey.com/Volume0/opasdata/d220001/derivates/1/008/957/MFG_WPSE471_sml%28200x200%29.jpg) | [Velleman Load Cell](https://www.digikey.com/en/products/detail/velleman/WPSE471/25965862) - $11.95 | Comes with ADC and is designed to work with load cells | Limited to 44 lbs; little more expensive than the other options |

**Optimal Choice:** *SparkFun Load Cell – 50 kg (Generic)*

**Rationale:** Provides great range, linear response, easy integration with ADC, and low cost.

---

## Component 2 — 5V Voltage Regulator

| Solution | Photo | Link & Cost | Pros | Cons |
|---|---|---|---|---|
| LM7805T | ![LM7805T](https://mm.digikey.com/Volume0/opasdata/d220001/derivates/1/100/625/374/296%7ET03B%7ENDE%7E3_sml.jpg) | [LM7805T](https://www.digikey.com/en/products/detail/texas-instruments/LM7805CT-NOPB/3901929) - $0.55 | - Robust and widely used <br>- Built-in thermal & short-circuit protection | - High dropout ~2 V <br>- Inefficient (wastes voltage as heat) |
| AMS1117-5.0 | ![AMS1117-5.0](https://mm.digikey.com/Volume0/opasdata/d220001/derivates/1/003/227/499/MFG_5272_AMS1117-5.0_primary_sml%28200x200%29.jpg) | [AMS1117-5.0](https://www.digikey.com/en/products/detail/evvo/AMS1117-5-0/24370130) - $0.12 | - Lower dropout (around 1.1 V) <br>- Very cheap & compact (SMD) | - Max ~1 A only <br>- Can run hot at high load |
| UA7805CKCS | ![UA7805CKCS](https://mm.digikey.com/Volume0/opasdata/d220001/derivates/1/300/702/797/296%7E4204749%7EKCS%7E3_sml.jpg) | [UA7805CKCS](https://www.digikey.com/en/products/detail/texas-instruments/UA7805CKCSE3/1494012) - $1.34 | - Handles up to 1.5 A <br>- Strong protection and reliability (classic 78xx design) | - Still high dropout (around 2 V) <br>- More expensive than AMS1117 |

**Optimal Choice:** *LM7805T*

**Rationale:** Offers fairly good stability; has pretty good current capacity; and is fairly reliable at a low cost.


## Component 3 — Operational Amplifier

| Solution | Photo | Link & Cost | Pros | Cons |
|----------|-------|-------------|------|------|
| **MCP6004** | ![MCP6004](https://mm.digikey.com/Volume0/opasdata/d220001/derivates/1/010/927/070/150%7EC04-005%7EP%2C-PD%7E14_sml.jpg) | [MCP6004](https://www.digikey.com/en/products/detail/microchip-technology/MCP6004-I-P/523060) - $0.59 | - Low power consumption (100 µA typical) <br> - Rail-to-rail input/output <br> - Wide supply voltage range (1.8V to 6.0V) | - High input offset voltage (~4.5 mV) <br> - Not suitable for low-level differential signals like load cells |
| **AD620ANZ** | ![AD620ANZ](https://mm.digikey.com/Volume0/opasdata/d220001/derivates/1/010/930/391/505%7EN-8%7EN%7E8-Top_sml.jpg) | [AD620ANZ](https://www.digikey.com/en/products/detail/analog-devices-inc/AD620ANZ/750967) - $17.22 | - Low input offset voltage (~50 µV) <br> - High common-mode rejection ratio (CMRR) <br> - Adjustable gain via external resistor | - Higher cost <br> - Single-channel amplifier |
| **INA333** | ![INA333](https://mm.digikey.com/Volume0/opasdata/d220001/derivates/1/300/760/263/296%7E4073329%7EDGK%7E8_sml.jpg) | [INA333](https://www.digikey.com/en/products/detail/texas-instruments/INA333AIDGKR/1886116) - $4.54 | - Lower offset voltage (+/- 25 nanoAmps) <br> - Lower quiescent current (1mA) <br> - More cost effective | - Lower maximum supply voltage <br> - Lower bandwidth |

**Optimal Choice:** *INA333*

**Rationale:** Low offset voltage; low quiescent current; lower cost than AD620ANZ.
