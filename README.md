# Simple MCP4251 Driver
This driver library provides basic functions for use with the MCP4251 digital potentiometers. This device has only been tested with the Arduino Uno/Nano boards with the chip enable pin set as D10.

## Functions
### MCP4251init()
- An initalizing function that sets the chip enable pin and enables SPI communications (uses the arduino SPI library).

### MCP4251increment(int wiperAddress)
- Increments the given **wiperAddress** as defined in the header file by 1.

### MCP4251decrement(int wiperAddress)
- Decrements the given **wiperAddress** as defined in the header file by 1.

### MCP4251writeData(int wiperAddress, uint16_t value)
- Writes **value** to the given wiperAddress as defined in the header file. Checks if the provided unin16_t value is greater than 255, in which case it is automatically set to the maximum value of the MCP4251 ([datasheet](https://ww1.microchip.com/downloads/aemDocuments/documents/OTH/ProductDocuments/DataSheets/22060b.pdf)).
