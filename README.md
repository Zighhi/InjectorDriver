# InjectorDriver

**Automotive 6-channel 24V injector driver with optional ECU signal inversion.**

This project is a hardware driver board designed to control 6 fuel injectors using peak-and-hold control, optimized for 24V systems. It is based on the LM1949 injector controller IC and includes an optional inversion circuit to accommodate ECU signal polarity differences.

The current version was **prototyped on a perfboard and hand-soldered**, intended for lab testing of different fueling strategies. A dedicated PCB design is planned for deployment use.

---

## Features

- 6 independent injector channels
- Peak & Hold current control
- Logic-level N-channel MOSFETs for low-loss switching
- Optional signal inversion using hex inverter + multiplexer
- Single switch toggles signal polarity across all channels
- Designed for automotive 24V rail operation

---

## Schematic Preview
![Docs/24V_InjectorDriver.png](/Docs/24V_InjectorDriver.png)
- Designed using **Altium Designer**
---

## Bill of Materials (BOM)


| Comment         | Designator                                         | Quantity |
|----------------|------------------------------------------           |----------|
| 100nF 12V       | C33–C35, C39–C41, C45–C47, C51–C53, C58, C63, C64  | 15 |
| 1uF 12V         | C36–C38, C48–C50, C57, C59, C62                    | 9       |
| 10nF 12V        | C42–C44, C54–C56                                   | 6       |
| 220nF 50V       | C60                                                | 1       |
| 100nF 50V       | C61                                                | 1       |
| 1N4937          | D13–D18                                            | 6       |
| 1N5819          | D19–D24                                            | 6       |
| LM1949N         | IC8–IC13                                           | 6       |
| 74HC04N         | IC14                                               | 1       |
| CD74HC157E      | U5, U6                                             | 2       |
| LM7805CT        | U4                                                 | 1       |
| DB9 Connector   | J4                                                 | 1       |
| Banana Jack     | J5, J6                                             | 2       |
| LED             | LED1                                               | 1       |
| Injector Conn.  | P7–P12                                             | 6       |
| BC547BG         | Q13–Q15, Q19–Q21                                   | 6       |
| IRL540N         | Q16–Q18, Q22–Q24                                   | 6       |
| 1kΩ 0.5W        | R20–R22, R29–R31, R38                              | 7       |
| 10kΩ 0.5W       | R23–R25, R32–R34                                   | 6       |
| 0.1Ω 2W         | R26–R28, R35–R37                                   | 6       |
| SPDT Switch     | SW2                                                | 1       |

---

## How It Works

1. **ECU control signals** are received for each injector channel.
2. A **global SPDT switch** selects between original and inverted signals.
3. Signals go through a **74HC157 mux** to the **LM1949** ICs.
4. Each LM1949 controls a **MOSFET** for Peak and Hold phases.
---

## License

This project is licensed under the [MIT License](./LICENSE).

---


