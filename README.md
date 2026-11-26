# LOBO MAX-80 · CPU Logic Board

This KiCad 10 project recreates the LOBO MAX-80 mainboard from the original schematics. The board contains the Z80B processor, main memory, serial interfaces, floppy disk controller, and video circuitry.

![Top view of the original LOBO MAX-80 CPU logic board](pcb_6.png)

The schematic spans five sheets. The PCB layout contains **228 footprints**. Routing is still pending.

## Opening the project

Open [MAX-80.kicad_pro](MAX-80.kicad_pro) in KiCad 10. Use the sheet hierarchy in the [top-level schematic](MAX-80.kicad_sch) to navigate between circuits. To inspect the board layout, open the [board file](MAX-80.kicad_pcb) in the PCB Editor.

## Schematic sheets and original scans

| Original sheet | Circuit | KiCad | Original scan |
| --- | --- | --- | --- |
| 1 | Z80B processor, system bus, and address decoding | [Schematic](MAX-80-Blatt-1.kicad_sch) | [Scan](1.png) |
| 2 | RAM, boot PROM, and real-time clock | [Schematic](MAX-80-Blatt-2.kicad_sch) | [Scan](2.png) |
| 3 | Serial interfaces and baud rate generator | [Schematic](MAX-80-Blatt-3.kicad_sch) | [Scan](3.png) |
| 4 | Floppy disk controller and drive connectors | [Schematic](MAX-80-Blatt-4.kicad_sch) | [Scan](4.png) |
| 6 | CRT controller, video memory, and video output | [Schematic](MAX-80-Blatt-6.kicad_sch) | [Scan](6.png) |

Original sheet 5 covers the computer’s second board, which carries the keyboard matrix, hard disk interface, and printer port. Its KiCad files are in the [Keyboard Logic Board project](../MAX-80_KEYBOARD/MAX-80-Keyboard.kicad_pro).

## Project libraries

The project uses KiCad’s standard libraries alongside the libraries registered in [sym-lib-table](sym-lib-table) and [fp-lib-table](fp-lib-table). The custom footprints are grouped into three directories.

| Footprint library | Contents |
| --- | --- |
| [MAX80_Edge.pretty](MAX80_Edge.pretty) | 34- and 50-contact card-edge connectors for the floppy drives |
| [MAX80_BoardParts.pretty](MAX80_BoardParts.pretty) | 40-contact expansion bus connector, RCA video jack, clock-set pushbutton, and DO-7 diode footprint |
| [MAX80_Passives.pretty](MAX80_Passives.pretty) | Trimmer capacitor for the real-time clock |

If the Footprint Browser reports a missing local library named `LICA MAX-80`, you can disable that entry in the project’s footprint library table. The three directories above contain all the custom MAX-80 footprints used on this board.

## Technical documentation

- [MAX-80 Technical Reference Manual (PDF)](Tech_Ref_Manual_Updated.pdf)
- [Appendix H – Original Schematics (PDF)](z80_Appendix_H_Schematics_Updated.pdf)
- [CPU logic board component placement diagram](CPU%20LOGIC%20Board.png)
