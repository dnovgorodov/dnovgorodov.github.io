---
title: Component Selection
---

## Component 1 — Load Cell (Weight Sensor)

| **Solution** | **Photo** | **Link & Cost** | **Pros** | **Cons** |
|---------------|------------|------------------|-----------|-----------|
| **SparkFun Load Cell – 50 kg (Generic)** | ![Generic](https://www.sparkfun.com/media/catalog/product/cache/a793f13fd3d678cea13d28206895ba0c/1/0/10245-01a.jpg) | [SparkFun Load Cell – 50 kg (Generic)](https://www.sparkfun.com/load-sensor-50kg-generic.html) — *$6.25* | Accurate (±0.02%), easy to mount, widely supported | Off-center loads reduce accuracy |
| **50kg Strain Gauge** | ![Strain Gauge](https://i.ebayimg.com/images/g/x~oAAOSw79Vm86qD/s-l1600.webp) | [Phidgets Micro Load Cell (0–50 kg)](https://www.ebay.com/itm/286077381781) — *$6.99* | High range, compact, reliable industrial supplier | Seems to be a lot of wiring |
| **Velleman WPSE471 Load Cell + ADC** | ![Velleman Load Cell](https://mm.digikey.com/Volume0/opasdata/d220001/derivates/1/008/957/MFG_WPSE471_sml%28200x200%29.jpg) | [Velleman Load Cell](https://www.digikey.com/en/products/detail/velleman/WPSE471/25965862) — *~$11.95 per gauge + materials* | Comes with ADC and is designed to work with load cells | Limited to 44 lbs; little more expensive than the other options |

**Optimal Choice:** *SparkFun Load Cell – 50 kg (Generic)*  
**Rationale:** Provides adequate range, linear response, easy integration with HX711 ADC, and low cost.

---

## Component 2 — 5V Voltage Regulator

| **Solution** | **Photo** | **Link & Cost** | **Pros** | **Cons** |
|---------------|------------|------------------|-----------|-----------|
| **LM7805** | ![LM7805](https://mm.digikey.com/Volume0/opasdata/d220001/derivates/1/100/625/374/296%7ET03B%7ENDE%7E3_sml.jpg) | [Texas Instruments LM7805 – Digi-Key](https://www.digikey.com/en/products/detail/texas-instruments/LM7805CT-NOPB/3901929) — **$0.50 – $1.00 USD** | The LM7805 is a very reliable and easy-to-use voltage regulator that provides a stable 5 V output with minimal external components. It includes built-in protection features such as thermal shutdown and short-circuit safety, making it a great choice for simple projects and educational use. | However, it is inefficient when the input voltage is much higher than 5 V, since the excess energy is dissipated as heat. It also typically requires a heatsink for high current applications and cannot supply more than about 1 A of current. |
| **AMS1117-5.0** | ![AMS1117](https://mm.digikey.com/Volume0/opasdata/d220001/derivates/1/003/227/499/MFG_5272_AMS1117-5.0_primary_sml%28200x200%29.jpg) | [AMS1117-5.0 – SparkFun](https://www.digikey.com/en/products/detail/evvo/AMS1117-5-0/24370130) — **$0.30 – $0.80 USD** | The AMS1117-5.0 is a compact low-dropout regulator that provides 5 V output with only about a 1.1 V difference required between input and output. It’s inexpensive, simple to use, and suitable for space-constrained projects that don’t need high current output. | Despite its small size, it suffers from poor heat dissipation and limited current handling (around 800 mA). It’s also not very efficient when used with higher input voltages, and can overheat if pushed too hard. |
| **LM2596** | ![LM2596](https://i.ebayimg.com/images/g/r6EAAOSww-1k6F9U/s-l1600.webp) | [LM2596 DC-DC Buck Converter Module](https://www.ti.com/lit/ds/symlink/lm2596.pdf) — **$1.50 – $3.00 USD** | The LM2596 is a highly efficient switching regulator that can provide up to 3 A of current with efficiency levels above 85%. It works well with a wide range of input voltages and is ideal for powering larger loads or battery-powered systems where efficiency is important. | On the downside, it produces more electrical noise than linear regulators, making it less suitable for sensitive analog circuits. It also requires more space and components, and its wiring is slightly more complex compared to simple linear regulators. |

**Optimal Choice:** *LM2596 DC-DC Buck Converter Module*

**Rationale:** The LM2596 was chosen as the optimal solution because it combines high efficiency with the ability to deliver more current (up to 3 A) while minimizing heat generation. Unlike linear regulators such as the LM7805 or AMS1117, it does not waste large amounts of energy as heat, making it ideal for systems powered by batteries or higher-voltage sources. Additionally, it supports a wide input voltage range, which provides flexibility for different power sources. While it produces more ripple than linear regulators, this can be managed with additional filtering if needed, and its overall efficiency and current capacity make it the best choice for most embedded projects.
