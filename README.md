# MakeCode Package for the Joy-IT SBC-RFID-RC522 RFID module (MFRC522).

This library provides a Microsoft Makecode package for the Joy-IT SBC-RFID-RC522 RFID module.
See https://joy-it.net/products/SBC-RFID-RC522 for more details.

## Connection

The RFID module needs to be connected with six pins to the Micro:bit:

| RFID module   | Micro:bit     |
| ------------- |:-------------:|
| VCC           | 3V            |
| GND           | GND           |
| MISO          | P15           |
| MOSI          | P14           |
| SCK           | P13           |
| NSS           | P16           |

## Initialize RFID module

The RFID module needs to be initialized before it is ready to use. All necessary commands will be transfered via SPI here.

```typescript
// Initialize RIFD module
MFRC522.Init()
```

## Read ID from card
This function reads the cards unique ID and returns it. This function blocks execution until a card is presented to the reader.

```typescript
// Read unique ID
MFRC522.getID()
```

## Read ID from card once
This function attempts to read the cards unique ID. In case a card is presented to the reader when the function is called, it returns the cards unique ID, otherwise it returns 0. This function does not block execution and should be called in a loop in order to detect the case when a card is presented to the reader.

```typescript
// Read unique ID once
MFRC522.getIDOnce()
```

## Read data from card
Data stored on the card can be retrieved with this function. This function blocks execution until a card is presented to the reader.

```typescript
// Read data
MFRC522.read()
```

## Read data from card once
This function attempts to read the data stored on the card. In case a card is presented to the reader when the function is called, it returns the data stored on the card, otherwise it returns `null`. This function does not block execution and should be called in a loop in order to detect the case when a card is presented to the reader.

```typescript
// Read data once
MFRC522.readOnce()
```

## Write data to card
Write data, formatted as string, to the card.

```typescript
// Write data
MFRC522.write("1234")
```

## Turn off antenna
After use, the antenn can be turned off.

```typescript
// Turn antenna off
MFRC522.AntennaOff()
```

## Supported targets

* for PXT/microbit

## License

MIT