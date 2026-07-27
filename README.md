# Custom PCB Design — Arduino Nano Clone

Full schematic and PCB layout design of an Arduino Nano–compatible board, designed
from scratch in KiCad, physically etched, soldered, and tested.

## What's Included
- `Arduino_Nano.kicad_sch` — full schematic
- `Arduino_Nano.kicad_pcb` — routed PCB layout (39 components placed)

## Key Components
- **ATmega328P** — main microcontroller
- **FT232RL** — USB-to-serial converter for programming/communication
- **LM1117MP-5.0** — 5V linear voltage regulator
- **USB Mini-B connector** — power and data
- **16MHz crystal resonator** — clock source
- Supporting passives: resistors, capacitors, status LEDs, polyfuse, reset switch

## How It Works
The design replicates the core architecture of an Arduino Nano: USB power and
serial communication are handled by the FT232RL, which bridges to the ATmega328P
over its UART pins for programming. The LM1117 regulates incoming USB 5V down to
a clean supply rail for the logic, with decoupling capacitors placed close to
each IC to maintain signal integrity. The resonator provides the microcontroller's
clock signal.

## Process
1. Schematic capture in KiCad — placing and wiring all components with correct
   pin assignments and power nets
2. PCB layout — routing traces, placing components, checking for clearance/DRC
   errors
3. Physical fabrication — etching the board
4. Assembly — soldering all components onto the etched board
5. Testing — verifying continuity and functionality of the assembled board

## Tech Stack
`KiCad` `PCB Design` `Schematic Capture` `Circuit Etching` `Soldering`

## What I Learned
Routing traces without accidental shorts was the hardest part of the layout stage —
with a board this dense (39 components including a microcontroller, USB-to-serial
chip, and voltage regulator), keeping enough clearance between traces while still
routing everything cleanly took several passes through KiCad's design rule checker.
Etching and soldering the physical board afterward made clear how much a clean
schematic and layout actually matters — any mistake at the design stage becomes a
much harder problem to fix once it's etched into copper.
