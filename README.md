# The GB Mini Flashable Camera
**A small flashable version of the original GameBoy Camera**

This project may still receive updates. The current release (1.3) has been produced, assembled and tested.
While earlier prototypes and this 1.3 release have all worked for me, I can't guarantee their working.
Assemble and use at your own risk. It is extremely easy to damage the MAC-GBD, FRAM and flash chip during assembly.

Note on assembly of the board. If you're using a new 3V0 regulator from the BOM list, the C16 capacitor will not be necessary. Unlike the original 3V0 regulator, the pin connected to this capacitor is NC on the new 3V0 regulator.

IMPORTANT note:
Some GameBoy cameras have the U4 regulator populated instead of the U5 regulator. My board is designed to work with either the regulator linked in the BOM (recommended) or the U5 regulator harvested from the original camera cart. U4 will not work.

## What to fit it with

The GB mini flashable camera in short version fits perfectly with the [Camera+ Mini shell](https://ko-fi.com/s/a4d7bd649a). With this shell, you can reuse the regular camera sensor ribbon.

The "Longboard" version has a "neck" that allows mounting it is a regular Game Boy Camera shell with the regular ribbon cable. If you change your idea, you can physically break the neck and adapt the PCB again in the [Camera+ Mini shell](https://ko-fi.com/s/a4d7bd649a).

In case you want to mount the short PCB in a regular camera shell or in the regular [Game Boy Camera+ shell](https://ko-fi.com/s/9457d1cc6e), you need a longer ribbon cable. 
Aliexpress cables are too thick for that task and you must order a genuine JST cable. The only available seller for replacement and longer cable is Digikey. Choose a [type B cable "socket to socket" ](https://www.digikey.fr/en/products/base-product/jst-sales-america-inc/455/A09ZR09Z/588181). The regular camera cable is [2 inches long](https://www.digikey.fr/en/products/detail/jst-sales-america-inc/A09ZR09ZR28H51B/6708551), so take at least a [4 inches one](https://www.digikey.fr/en/products/detail/jst-sales-america-inc/A09ZR09ZR28H102B/9972202).

The PCBs come with pads for both vertical and horizontal SMD JST connectors. Be sure to solder on the right pads to avoid polarity inversion. **For the Camera+ mini shell and short PCB, it is recommended to go with the horizontal socket as there is not too much room inside.**

![](/Connector.png)

Please follow the [building instructions](/build.pdf) for PCB ordering options. Use [JLCPCB](https://passport.jlcpcb.com/) for ordering. They offer VAT compliant services for European customers and very cheap shipping options.

## Component location on PCB (short version)

![](/Component_placement.png)

## Component list (both versions)

|Reference	|Value	|Count	|Footprint	|Name	|Description|
|-----------|----------|-----------|----------------|-------------|------------------|
|C2, C3, C4, C5, C6, C7, C8, C9, C12, C13, C14, C15, C16, C17	|10nF	|14	|0603 (imperial)|	Capacitor Ceramic (X7R)|	Decoupling Capacitor|
|C10, C11, C18	|22pF	|3	|0603 (imperial)	|Capacitor Ceramic (X7R)|	Decoupling Capacitor|
|C17	|22uF	|1	|1206 (imperial)	|Capacitor Tantalum (≤10%)	|Filtering Capacitor|
|C1	|100nF	|1	|0603 (imperial)	|Capacitor Ceramic (X7R)	|Decoupling Capacitor|
|D1	|N/A	|1	|SOT-23	|BAT54W-HG3-18 (or BAT 63-02V H6327 )	|Schottky diode|
|J2	|N/A	|1	|N/A	|JST ZH1.5mm (9 pins)	|Camera Connector (male)|
|R1	|1kΩ	|1	|0603 (imperial)	|Resistor	|Resistor|
|U1	|N/A	|1	|TQFP-100 (14x14mm)	|Reuse from original cart (U1)	|Main gamecart chip|
|U2	|N/A	|1	|SC-88A-5 	|M74VHC1GU04DFT1G-L22038	|Signal inverter|
|U3	|N/A	|1	|TSOP-I-32 (12.4x8mm)	|FM28V100-TG 	|FRAM|
|U4	|N/A	|1	|SOT-23-5	|NCP718ASN300T1G 	|3V0 voltage regulator|
|U5	|N/A	|1	|TSOP-I-40 (18.4x10mm)	|AM29F080B	|Flash memory|

## Notes
- the AM29F080B is discontinued but easy to find on Aliexpress for cheap
- Low voltage Schottky diode can be hard to find but any equivalent one will do the job. The original camera used a Panasonic MA784 (discontinued), you can take inspiration from its datasheet.
