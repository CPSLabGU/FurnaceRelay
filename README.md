# FurnaceRelay

This repository contains the source files for the *FurnaceRelay* example provided in Chapter 5 of my PhD.
The folder structure contains the machine source files within `FurnaceRelay.machine` and images of the Kripke
structure within the `verification` folder.
```
.
├── FurnaceRelay.machine
│   ├── data.dat
│   ├── model.json
│   └── output.json
├── README.md
└── verification
    ├── graph.dot
    ├── graph.pdf
    ├── graph.png
    ├── graph.svg
    └── spec.tctl
```
The `FurnaceRelay.machine` folder contains 3 files — `data.dat`, `model.json`, and `output.json`.
The `model.json` file represents the user-input from the [LLFSM editor](https://github.com/CPSLabGU/editor) and
is the core source file that is modified during the machine design.
The `data.dat` file represents the binary-encoded Kripke structure transferred from the FPGA, and `output.json` is
the decoded form.

The verification folder contains visual representations of the Kripke structure defined in `data.dat` and `output.json`.
You will find images called `graph` accross multiple respective image formats. The `graph.dot` file specifies the
original image as a [graphviz](https://graphviz.org) graph.
Lastly, the `spec.tctl` shows a dummy specification written in `TCTL` which is then parsed and verified using the
[LLFSM Model Checker](https://github.com/CPSLabGU/VHDLModelChecker).
You may perform the verification after installing the `llfsm-verify` binary via:

```
llfsm-verify --machine FurnaceRelay.machine verification/spec.tctl
```
