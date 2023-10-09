# DBC File

Hyundai Kona Electric DBC file, work in progress.

## Conventions

Messages copied from other sources may not follow these conventions (yet!)

### CAN Message Names

* Message naming follows convention `SourceModule_HEXID`, i.e. `VCU_333` is ID 0x333 sent by VCU (Vehicle Control Unit).
* To make it quicker to find some messages, some are named `SourceModule_HEXID_Name`, i.e. `VCU_523_TEMP` is temperature information sent on ID 0x523 by VCU.
* Most of these IDs are found on the PCAN bus. For IDs seen on other buses, add another letter i.e. `SMK_B112` is ID 0x112 sent by SMK (Smart Key Module) on the BCAN bus. If the message also appears on the PCAN bus then the letter should be removed, and can optionally add a comment about which bus(es) it is forwarded onto. So far I haven't see any places where the same ID is used for two different messages depending on the bus, but this probably happens at least somewhere...
* `UNK` stands for unknown, i.e. `UNK_471` is ID 0x471 sent by an unknown module.

## Resources

This file includes information pieced together from the following sources, as well as the logs in this repo. Massive gratitude to everyone who has worked on decoding Hyundai/Kia CAN messages, and/or who has posted CAN logs from vehicles online!

* comma.ai opendbc repo [hyundai_kia_generic.dbc](https://github.com/commaai/opendbc/blob/master/hyundai_kia_generic.dbc).
* [uhi22](https://openinverter.org/forum/memberlist.php?mode=viewprofile&u=1960)'s [Ioniq DBC file](https://github.com/uhi22/IoniqMotorCAN/tree/master/Traces).
* Eric Router's [spreadsheet](https://docs.google.com/spreadsheets/d/1nDxmM4uLwufTUaGpi_X94d79ptCv5niia4NZ-SJZmJ8/edit#gid=0) of PCAN messages, see also [this comment](https://www.reddit.com/r/CarHacking/comments/llooxp/comment/gnr0prk/). Eric also did a bunch of VESS hacking ([code](https://github.com/ereuter/vess), [video](https://www.youtube.com/watch?v=OLT1aKdpYhs)).
* "vin" on openinverter's CAN log for [2020 Ioniq BMU with nothing else connected](https://openinverter.org/forum/viewtopic.php?p=45544#p45544).
* "powertop" on openinverter has a [spreadsheet with CAN message content summaries here](https://docs.google.com/spreadsheets/d/1dbOT9I-Aj7lU7yCiJDpXERjYRVOL_M1Tm2QFgmyYt4Y/edit#gid=0) (see also [post](https://openinverter.org/forum/viewtopic.php?p=54257#p54257)).
* [Kia Soul EV Message spreadsheet](https://docs.google.com/spreadsheets/d/1YYlZ-IcTQlz-LzaYkHO-7a4SFM8QYs2BGNXiSU5_EwI/edit#gid=0) (dates from ~2016 or so, author and relevance to Kona are both currently unknown!)

Where possible the git log for the DBC file includes some comments on what the source for a particular addition or change is.

## License

To any extent applicable, any DBC files in this directory are licensed under the MIT License (same as opendbc project) with the following applicable text:

---

Copyright (c) 2023, Angus Gratton and others.

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

---

Note: For Copyright purposes, I don't consider this DBC file to be a "derived work" of any of the linked information resources. DBC file content is mostly simple facts, which are generally not copyrightable on their own. The information we're collecting here is an aggregation of simple facts  - i.e. message X field Y means Z. In the same spirit, if you take information from this DBC and apply it somewhere else - that isn't copying the entire file - then I don't believe you need to worry about the source copyright or DBC file license information. Of course, I'm very grateful if you re-share your work and credit the sources you got it from - that's the decent thing to do, regardless!
