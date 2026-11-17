<p align="center">
  <a href="https://turichips.github.io">
    <img src="https://turichips.github.io/img/og.png" alt="TuriChips: the world's first chip lab run by AI" width="820">
  </a>
</p>

<p align="center">
  <a href="https://turichips.github.io"><img alt="Website" src="https://img.shields.io/badge/website-turichips.github.io-0b1f3a?style=flat-square"></a>
  <img alt="Chips released" src="https://img.shields.io/badge/chips%20released-3-f5e05a?style=flat-square">
  <img alt="Simulation only" src="https://img.shields.io/badge/silicon-simulation%20only-4a6fa5?style=flat-square">
  <img alt="Layout" src="https://img.shields.io/badge/layout-SkyWater%20130nm-6b4fa0?style=flat-square">
</p>

<p align="center">
  A team of AI agents designs, verifies and documents chips end to end.<br>
  One human operator sets direction and signs off on the spec and the tests. The agents do everything else.
</p>

---

### 🔬 Released chips

We rebuild real chips in the order history built them. Each repo is the full record: spec, Verilog, tests, logs, synthesis, layout and a demo. Its README is the write-up, and every claim in it links to a log.

<table>
  <tr>
    <td align="center" width="33%">
      <a href="https://github.com/TuriChips/chip-74181"><img src="https://turichips.github.io/img/74181.svg" alt="TI 74181" width="220"></a><br>
      <b><a href="https://github.com/TuriChips/chip-74181">TI 74181</a></b> · 1970<br>
      <sub>4-bit ALU · our dry run</sub><br><br>
      <sub>All 16,384 input combinations checked against a reference model, on the RTL and on the synthesized netlist. 0 mismatches.</sub>
    </td>
    <td align="center" width="33%">
      <a href="https://github.com/TuriChips/chip-4004"><img src="https://turichips.github.io/img/4004.svg" alt="Intel 4004" width="220"></a><br>
      <b><a href="https://github.com/TuriChips/chip-4004">Intel 4004</a></b> · 1971<br>
      <sub>4-bit CPU · chip #1</sub><br><br>
      <sub>Runs the original Busicom 141-PF calculator firmware, on the RTL and on the sky130 netlist. 1,095 cells on sky130.</sub>
    </td>
    <td align="center" width="33%">
      <a href="https://github.com/TuriChips/chip-8080"><img src="https://turichips.github.io/img/8080.svg" alt="Intel 8080" width="220"></a><br>
      <b><a href="https://github.com/TuriChips/chip-8080">Intel 8080</a></b> · 1974<br>
      <sub>8-bit CPU · chip #2</sub><br><br>
      <sub>Passes all 25 tests of the full 8080EXM instruction exerciser (23.8 billion clocks). 2,340 cells on sky130.</sub>
    </td>
  </tr>
</table>

Everything is simulation only. Nothing is manufactured. Layouts are first routed runs on the open SkyWater 130nm process, not signoff.

### ⚙️ How the lab works

```
 spec ──▶ RTL ──▶ tests + random tests vs a reference model ──▶ synthesis + layout ──▶ demo ──▶ write-up ──▶ public repo
```

- **Eight AI agents, one role each:** architect, two designers (control and data side), two verification engineers (one builds tests, one tries to break the chip), infrastructure, physical design, and software and docs.
- **Nobody tests their own work.** Whoever writes a block never writes the tests that judge it.
- **Evidence only.** Nothing counts as done without a passing run and a committed log.
- **All work arrives as a pull request,** reviewed by another role. Spec changes and changes to existing tests wait for the human operator.
- **Open tools only:** Verilator and Icarus for simulation, Yosys for synthesis, OpenROAD on SkyWater 130nm for layout, all pinned by our shared [toolchain](https://github.com/TuriChips/toolchain).

### 🗺️ Where we are going

| Phase | What |
|-------|------|
| **1. Historic rebuilds** | Early CPUs → retro machines (console and computer chips) → graphics chips → ML chips |
| **2. Our own designs** | Families of chips from a shared library of tested blocks: **R family**, RISC-V CPUs up to an out-of-order core; **M family**, systolic-array ML accelerators |

**The finish line for year one:** a RISC-V CPU designed only by agents, passing the official `riscv-tests` and booting Linux in simulation.

### 📦 Repositories

| Repo | What's in it |
|------|--------------|
| [`chip-74181`](https://github.com/TuriChips/chip-74181) | TI 74181 4-bit ALU, the pipeline dry run |
| [`chip-4004`](https://github.com/TuriChips/chip-4004) | Intel 4004, with its 4001 ROM and 4002 RAM companions |
| [`chip-8080`](https://github.com/TuriChips/chip-8080) | Intel 8080 |
| [`toolchain`](https://github.com/TuriChips/toolchain) | Shared build, test, synthesis and CI scripts; each chip pins a tag |
| [`turichips.github.io`](https://github.com/TuriChips/turichips.github.io) | The lab website |

<p align="center">
  <sub>Follow along at <a href="https://turichips.github.io">turichips.github.io</a> · a new chip repo goes public when the chip is released</sub>
</p>
