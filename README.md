# GB_Mini_Camera
A smaller flashable version of the original GameBoy Camera

This project may still receive updates. The current release (1.3) has been produced, assembled and tested.
While earlier prototypes and this 1.3 release have all worked for me, I can't guarantee their working.
Assemble and use at your own risk. It is extremely easy to damage the MAC-GBD, FRAM and flash chip during assembly.

Note on assembly of the board. If you're using a new 3V0 regulator from the BOM list, the C16 capacitor will not be necessary. Unlike the original 3V0 regulator, the pin connected to this capacitor is NC on the new 3V0 regulator.

IMPORTANT note:
Some GameBoy cameras have the U4 regulator populated instead of the U5 regulator. My board is designed to work with either the regulator linked in the BOM (recommended) or the U5 regulator harvested from the original camera cart. U4 will not work.

![](/Component_placement.png)

##Component list

|Reference	|Value	|Count	|References	Footprint	Name	Description		Inverter Alternatives:
C2, C3, C4, C5, C6, C7, C8, C9, C12, C13, C14, C15, C16, C17	10nF	14	C2, C3, C4, C5, C6, C7, C8, C9, C12, C13, C14, C15, C17, C19	0603 (imperial)	Capacitor Ceramic (X7R)	Decoupling Capacitor		74LVC1G06SE-7
C10, C11, C18	22pF	3	C10, C11, C18	0603 (imperial)	Capacitor Ceramic (X0G/NP0)	Signal shift capacitor		74AHC1G04SE-7
C17	22uF	1	C17	1206 (imperial)	Capacitor Tantalum (?10%)	Filtering Capacitor		TC7S04FU,LF
C1	100nF	1	C1	0603 (imperial)	Capacitor Ceramic (X7R)	Decoupling Capacitor		
D1	N/A	1	D1	SOT-23	BAT54W-HG3-18 (or BAT 63-02V H6327 )	Schottky diode		
J2	N/A	1	J2	N/A	JST ZH1.5mm (9 pins)	Camera Connector (male)		
R1	1k?	1	R1	0603 (imperial)	Resistor	Resistor		
U1	N/A	1	U1	TQFP-100 (14x14mm)	Reuse from original cart (U1)	Main gamecart chip		
U2	N/A	1	U2	SC-88A-5	M74VHC1GU04DFT1G-L22038	Signal inverter		
U3	N/A	1	U3	TSOP-I-32 (12.4x8mm)	FM28V100-TG	FRAM		
U4	N/A	1	U4	SOT-23-5	NCP718ASN300T1G	3V0 voltage regulator		
U5	N/A	1	U5	TSOP-I-40 (18.4x10mm)	AM29F080B	Flash memory		
