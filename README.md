# CFET_fp

## Overview

This project offers standard cells generated by *CFET_fp*, which utilizes a search-tree based approach for transistor placement combined with multi-row-aware folding and an SMT-based in-cell routing. 

The cells are developed using [ASAP7 PDK library](https://github.com/The-OpenROAD-Project/asap7).
The FEOL layers in the cell GDS (including BPN, special vias, etc.) are arbitrarily chosen.


For more information, refer to the paper:
* *Suwan Kim and Taewhan Kim, Optimal Transistor Folding and Placement for Synthesizing Standard Cells of Complementary FET Technology, IEEE/ACM Design Automation Conference (DAC), Jun. 2024.*

## Architecture and Standard Cell Information
We have created four sets of CFET cell libraries: (1) 2-track multi-row, (2) 3-track multi-row, (3) 4-track single-row, and (4) 4-track multi-row.

The rules for each CFET cell library are outlined below:

* Rules for (1) and (2):
```
P-FET on N-FET
Minimum area rule (MAR) = 1
End-of-line (EOL) = 1
Via rule (VR) = 0
Parallel run length (PRL) = 1
Step height rule (SHR) = 2
Minimum pin length (MPL) = 1(for (1)), 2(for (2))
```

* Rules for (3) and (4):
```
N-FET on P-FET
Minimum area rule (MAR) = 1
End-of-line (EOL) = 2
Via rule (VR) = 1
Parallel run length (PRL) = 1
Step height rule (SHR) = 2
Minimum pin length (MPL) = 2
```

For (1), (2), and (3), the following 30 cells have been generated:
```
AND2x2 AND3x1 AND3x2 AOI21x1 AOI22x1 
BUFx2 BUFx3 BUFx4 BUFx8
DFFHQNx1 DFFHQNx2 DFFHQNx3 FAx1 
DHLx1 DHLx2 DHLx3
INVx1 INVx2 INVx4 INVx8
NAND2x1 NAND2x2 NAND3x1 NAND3x2
NOR2x1 NOR2x2 NOR3x1 NOR3x2
OAI21x1 OAI22x1 OR2x2 OR3x1 OR3x2 
XNOR2x1 XOR2x1
```
