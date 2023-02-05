# GB_Mini_Camera
**A smaller flashable version of the original GameBoy Camera**

## Versions:

### GBC_V2.0
* Most compact out of the box
* No ROM switch
* No sensor footprint
* Compatible with [Camera+ mini](https://ko-fi.com/s/a4d7bd649a)
* Compatible with [Camera+](https://ko-fi.com/s/9457d1cc6e) (requires custom extended sensor cable)

### GBC_SENS_V2.0
* Not as compact out of the box
* Footprint for ROM switch
* Footprint for camera sensor
* Compatible with [Camera+ mini](https://ko-fi.com/s/a4d7bd649a)
* Compatible with [Camera+](https://ko-fi.com/s/9457d1cc6e) (requires custom extended sensor cable)
* Compatible with [Game Boy Mini Camera](https://gameboycamera.super.site/projects/game-boy-mini-camera) (By Christopher Graves)

## Assembly notes

### Project difficulty
This project may be difficult to complete. It requires precise soldering of delicate components.
It is remarkably easy to damage sensitive components in the process (Flash memory, FRAM, MAC-GBD).
Assemble at your own risk. For support you may turn to the GameBoy Camera discord community.

### Note: voltage regulator
* The voltage regulator may be harvested from an original GameBoy camera cartridge, **only** if it populates U5 on the original PCB.
	* When the U5 voltage regulator is used, C5 on the project PCB will have to be populated.
	* When a voltage regulator from the BOM is used, do **not** populate C5 on the project PCB.

### Note: solder jumpers
The project PCBs currently contain two **optional** solder jumpers. These should only be bridged under certain circumstances.
* JP1 **must** be bridged when:
	* U2 and C4 remain unpopulated, bypassing the signal inverter.
	
* JP2 **must** be bridged when:
	* There's no ROM switch installed (this will limit the cart to a single ROM
	
### Note: C14
**Leave C14 unpopulated**