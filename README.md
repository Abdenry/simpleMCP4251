# Simple MCP4251 Driver
This driver library provides basic functions for the MCP4251 digital potentiometers. 

## Functions
### MCP4251init()
An initalizing function that sets the chip enable pin and enables SPI communications (uses the arduino SPI library).

```
MCP4251init();
```

### MCP4251increment(int wiperAddress)
Increments the given **wiperAddress** as defined in the header file by 1.
```
MCP4251increment(WIPER0ADD);
```

### MCP4251decrement(int wiperAddress)
Decrements the given **wiperAddress** as defined in the header file by 1.
```
MCP4251decrement(WIPER0ADD);
```

### MCP4251writeData(int wiperAddress, uint16_t value)
Writes **value** to the given wiperAddress as defined in the header file. Checks if the provided unin16_t value is greater than 255, in which case it is automatically set to the maximum value of the MCP4251 ([datasheet](https://ww1.microchip.com/downloads/aemDocuments/documents/OTH/ProductDocuments/DataSheets/22060b.pdf)).
```
MCP4251writeDattta(WIPER0ADD, 257);
```

# Wiring Diagram
| PIN | MCP42X1 | Arduino Nano |
| --- | --- | ---|
| 1 | CS | D10 |
| 2 | SCK | D13 |
| 3 | SDI | D11 |
| 4 | Vss | GND |
| 5 | P1B | USER DEF |
| 6 | P1W | USER DEF |
| 7 | P1A | USER DEF |
| 8 | P0A | USER DEF |
| 9 | P0W | USER DEF |
| 10 | P0B | USER DEF |
| 11 | WP | - |
| 12 | SHDN | - |
| 13 | SDO | - |
| 14 | Vdd | +5V |

Note: User defined pins (Pin 5 - 10) are to be set based on the users application. They are equivalent to analogue potentiometer legs.
