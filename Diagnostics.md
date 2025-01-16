# UDS Diagnostic IDs

Table of which *diagnostic* CAN IDs correspond to which modules. (Note: Diagnostic CAN IDs are totally separate from CAN messaging during normal vehicle operation.)

Each module has an `rxid` which receives UDS messages and it responds by sending messages to a `txid`. `rxid == txid + 8`.

| RXID  | TXID  | Module           | Notes                 |
|-------|-------|------------------|-----------------------|
| 0x71d | 0x715 | EWP (BMS)??      |                       |
| 0x72d | 0x725 | ?                |                       |
| 0x73b | 0x733 | ?                |                       |
| 0x74e | 0x746 | EWP (Inverter)?? |                       |
| 0x778 | 0x770 | IGPM (Gateway)   |                       |
| 0x79e | 0x796 | ?                |                       |
| 0x7a8 | 0x7a0 |                  |                       |
| 0x7ad | 0x7a5 |                  |                       |
| 0x7bb | 0x7b3 | Air Conditioner  |                       |
| 0x7bf | 0x7b7 |                  |                       |
| 0x7ce | 0x7c6 | Cluster          |                       |
| 0x7dc | 0x7d4 | ?                |                       |
| 0x7ea | 0x7e2 | Maybe EPCU       |                       |
| 0x7eb | 0x7e3 | EPCU             |                       |
| 0x7ec | 0x7e4 | BMU              | (can read/erase DTCs) |
| 0x7ed | 0x7e5 | OBC              |                       |
