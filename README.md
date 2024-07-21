# The GB Mini Flashable Camera - a friendly fork
**A small flashable version of the original GameBoy Camera. This fork was made for my own use without any supervision or feed back from the original author. Any opinion expressed is mine and mine only.**

Want to make a flashable Game Boy camera without giving a single cent to assholes ? This project is for you !

The current release (1.3) has been produced, assembled and tested. It is extremely easy to damage the MAC-GBD, FRAM and flash chip during assembly, this project is **definitely not recommended** for beginners. The board is compatible with any regular camera rom (Game Boy Camera, Pocket Camera, Hello Kitty, Zelda special edition and [Debagame tester](https://tcrf.net/Proto:Game_Boy_Camera)) and homebrews like [Photo!](https://github.com/untoxa/gb-photo) or [2bit PXLR Studio](https://github.com/HerrZatacke/2bit-pxlr-studio). It is recommended to flash this board with a [GBxCart](https://www.gbxcart.com/) and [FlashGBX](https://github.com/lesserkuma/FlashGBX) as support is guaranteed. Other devices (Cyclones, GB Operator, etc.) were not tested. May or may not work, I have no idea.

## What to fit it with

The GB mini flashable camera in short version fits perfectly with the [Camera+ Mini shell](https://ko-fi.com/s/a4d7bd649a). With this shell, you can reuse the regular camera sensor ribbon.

The "Longboard" version has a "neck" that allows mounting it is a regular Game Boy Camera shell with the original ribbon cable. If you change your idea, you can physically break the neck and adapt the PCB again in the [Camera+ Mini shell](https://ko-fi.com/s/a4d7bd649a). **The long neck must be used with a vertical SMD JST connector.**

Both versions come with pads for both vertical and horizontal SMD JST connectors on the short part (before the neck). Be sure to solder the right connector on the right pad to avoid polarity inversion. **For the Camera+ mini shell and short PCB, it is recommended to go with the horizontal socket as there is not too much room inside.**

I overall recommend to order the long board which is more versatile by default.

In case you want to mount the short PCB in a regular camera shell or in the regular [Game Boy Camera+ shell](https://ko-fi.com/s/9457d1cc6e), you will need a longer ribbon cable. 
Aliexpress cables are too thick and crappy for that task and you must order a genuine JST cable. Sadly for Eu customers, the only available seller for replacement and longer cable is Digikey. Choose a [type B cable "socket to socket" ](https://www.digikey.fr/en/products/base-product/jst-sales-america-inc/455/A09ZR09Z/588181). The regular camera cable is [2 inches long](https://www.digikey.fr/en/products/detail/jst-sales-america-inc/A09ZR09ZR28H51B/6708551), so take at least a [4 inches one](https://www.digikey.fr/en/products/detail/jst-sales-america-inc/A09ZR09ZR28H102B/9972202).

![](/Connector.png)

Please follow the [building instructions from the original author](/build.pdf) for PCB ordering options. Use [JLCPCB](https://passport.jlcpcb.com/) for ordering if you live in Europe. They offer VAT compliant services for European customers and very cheap shipping options.

**IMPORTANT note:** some GameBoy cameras have the U4 regulator populated instead of the U5 regulator. My board is designed to work with either the regulator linked in the BOM (recommended) or the U5 regulator harvested from the original camera cart. **U4 from the original board will not work.** If you're using a new 3V0 regulator from the BOM list, the **C16 capacitor will not be necessary.** Unlike the original 3V0 regulator, the pin connected to this capacitor is NC on the new 3V0 regulator.

## Component location and orientation on PCB (short version)

![](/Component_placement_w_components.png)

## Component list (both versions)

|Reference	|Value	|Count	|Footprint	|Name	|Description|
|-----------|----------|-----------|----------------|-------------|------------------|
|C2, C3, C4, C5, C6, C7, C8, C9, C12, C13, C14, C15, C16, C19	|10nF	|14	|0603 (imperial)|	Capacitor Ceramic (X7R)|	Decoupling Capacitor|
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
- The AM29F080B is discontinued but easy to find on Aliexpress for cheap (batches are mainly recycled chips). It can be fun to dump the content to see what was the chip usage before its recycling.
- Some versions of the FM28V100-TG by Cypress semiconductors come without a dot to indicate pin 1 but only a side notch. The side notch also indicates the row where pin 1 is located, so it must be soldered with notch pointing down (same as the dot if present).
- The M74VHC1GU04DFT1G signal inverter is becoming hard to source in 2024 so it is recommended to switch to a MC74VHC1GU04DF1G (same pinout, same characteristics). The SC-88 package version is quite hard to find on Aliexpress but available on Mouser and Digikey. Chip marking must be **V6** in case of doubt when receiving the order.
- Low voltage Schottky diode can also be hard to find but any equivalent one will do the job. The original camera used a Panasonic MA784 with marking **2D** (discontinued), among other undocumented variations, you can take inspiration from its datasheet. The RB510VM-30 is a possible candidate for example. It must have the lowest possible forward voltage drop.
- Most parts can be found on Aliexpress, Mouser and Digikey except for the ribbon cable (Digikey only) if you need a longer one.
- You can easily desolder the MAC-GBD by using a hot air gun (set at 350°C maximum) on the back side of the original board until the chip falls by itself. This is by far the most secure way I've found. I do not recommend using low temp solder or other bismuth containing crap. No need. The author of the original project recommends using a heating plate set at 250°C.
- Lead free solder in wire is really crap and will be a pain to use. Either use old good lead/tin alloy with flux core if you can find some or lead free solder paste. And always remind the rule of thumb when using flux: "the bigger the blob, the better the job".
- The ferrite beads have been removed even if they are still mentioned in the pdf desciption of the project.
- The schematic is precise enough to troubleshoot any issue with a multimeter in continuity mode.

## Why I won't provide any furher help on this fork
I wasted uncountable hours helping people with flashable camera projects sometimes without receiving any thank in return. I've made many flashable cameras for free, even sacrifying some of my own cameras in case something went wrong on my side. I've actively contributed to [Photo!](https://github.com/untoxa/gb-photo), the flashable camera custom rom, all on my free time and hollidays. My reward ? Public defamation on social media by some well known scumbags of the Game Boy retro "community". I've really had enough of all that shit at a certain point. So you're on your own with this project, try to contact the original author for issues but he is probably as pissed as I am for the same reasons.

## Acknoledgements
- [Andreas Hahn](https://github.com/HerrZatacke) and [Mraulio](https://github.com/Mraulio) for helping me to complete this fork with relevant informations I did not have initially.
- [2BitWizard](https://github.com/2BitWizard) for completing the project to its end despite being insulted online by members of the Game Boy retro "community" all along the process. Thanks also for sending me prototype boards.
