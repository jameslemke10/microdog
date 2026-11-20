# Audio

The Pi 5 has no headphone jack, so Microdog uses the Pi's I2S bus for both its ears and its voice. That means no USB sound card and no extra battery tap.

| Part | Qty | Wiring |
|---|---|---|
| INMP441 I2S mic | 2 (stereo) | One board's **L/R pin to GND** (left), the other's **L/R to 3.3 V** (right). Both get 3.3 V and GND from the Pi. Solder on the loose header pins. |
| MAX98357A I2S amp | 1 | **VIN from the 5 V regulator**, not the Pi's 5 V pins |
| 4 Ω 3 W speaker | 1 | Cut off the JST plug and screw the bare wires into the amp's terminal |

## Pins

These are the standard Pi I2S pins. Confirm them on the bench before trusting them.

| Signal | Pi GPIO | Mics | Amp |
|---|---|---|---|
| Bit clock | GPIO18 | SCK | BCLK |
| Word select | GPIO19 | WS | LRC |
| Data into Pi | GPIO20 | SD (both mics) | — |
| Data out of Pi | GPIO21 | — | DIN |

Still TBD: the device-tree overlay that gives simultaneous capture and playback on one I2S bus, and the amp gain and SD-mode pin settings. Update this page once a loopback test (mic → speaker) works.
