# DBC File

Reverse engineered Hyundai Kona Electric DBC file(s), work in progress.

* `pcan.dbc` applies to PCAN (Powertrain) CAN Bus. This is where most of the effort has been put in. Some messages have comments indicating if the same message is forwarded unmodified to multiple buses.
* `bcan.dbc` applies to BCAN (Body) CAN Bus.
* `comp_can.dbc` applies to the "COMP CAN" bus that links the A/C controller (FATC), A/C compressor and the PTC heater modules only.

## Conventions

Messages copied from other sources may not follow these conventions (yet!)

### CAN Message Names

* Currently the message naming follows convention `SourceModule_HEXID`, i.e. `VCU_333` is ID 0x333 sent by VCU (Vehicle Control Unit).
* To make it quicker to find some messages, some are named `SourceModule_HEXID_Name`, i.e. `VCU_523_TEMP` is temperature information sent on ID 0x523 by VCU.
* `UNK` stands for unknown, i.e. `UNK_471` is ID 0x471 sent by an unknown module.

## Resources

This file includes information pieced together from the following sources. Massive gratitude to everyone who has worked on decoding Hyundai/Kia CAN messages, and/or who has posted CAN logs from vehicles online!

* Large body of CAN logs hosted at https://github.com/projectgus/hyundai-kona-ev-can-logs/
* comma.ai opendbc repo [hyundai_kia_generic.dbc](https://github.com/commaai/opendbc/blob/master/hyundai_kia_generic.dbc).
* [uhi22](https://openinverter.org/forum/memberlist.php?mode=viewprofile&u=1960)'s [Ioniq DBC file](https://github.com/uhi22/IoniqMotorCAN/tree/master/Traces).
* Eric Router's [spreadsheet](https://docs.google.com/spreadsheets/d/1nDxmM4uLwufTUaGpi_X94d79ptCv5niia4NZ-SJZmJ8/edit#gid=0) of PCAN messages, see also [this comment](https://www.reddit.com/r/CarHacking/comments/llooxp/comment/gnr0prk/). Eric also did a bunch of VESS hacking ([code](https://github.com/ereuter/vess), [video](https://www.youtube.com/watch?v=OLT1aKdpYhs)).
* "vin" on openinverter's CAN log for [2020 Ioniq BMU with nothing else connected](https://openinverter.org/forum/viewtopic.php?p=45544#p45544).
* "powertop" on openinverter has a [spreadsheet with CAN message content summaries here](https://docs.google.com/spreadsheets/d/1dbOT9I-Aj7lU7yCiJDpXERjYRVOL_M1Tm2QFgmyYt4Y/edit#gid=0) (see also [post](https://openinverter.org/forum/viewtopic.php?p=54257#p54257)).
* [Kia Soul EV Message spreadsheet](https://docs.google.com/spreadsheets/d/1YYlZ-IcTQlz-LzaYkHO-7a4SFM8QYs2BGNXiSU5_EwI/edit#gid=0) (dates from ~2016 or so, ayqyuthor and relevance to Kona are both currently unknown!)

Where possible the git log for the DBC file includes some comments on what the source for a particular addition or change is. 

## License

To any extent applicable, these DBC files are licensed under the MIT License as described in the file LICENSE.

Please note very carefully the disclaimer of warranty in the MIT License. These DBC files are the product of reverse engineering and should be regarded as completely untrustworthy!

Note: For Copyright purposes, I don't consider this DBC file to be a "derived work" of any of the linked information resources. DBC file content is mostly simple facts, which are generally not copyrightable on their own. The information we're collecting here is an aggregation of simple facts  - i.e. message X field Y means Z. In the same spirit, if you take information from this DBC and apply it somewhere else - that isn't copying the entire file - then I don't believe you need to worry about the source copyright or DBC file license information. Of course, I'm very grateful if you re-share your work and credit the sources you got it from - that's the decent thing to do, regardless!
