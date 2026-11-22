# makefun-tiny-stack-vm

[![make.fun · tiny-stack-vm-01-run-20261122](https://make.fun/badge/tiny-stack-vm-01-run-20261122.svg)](https://make.fun/bounty/tiny-stack-vm-01-run-20261122?utm_source=github&utm_medium=readme&utm_campaign=tiny-stack-vm-01-run-20261122)
[![rank](https://make.fun/badge/tiny-stack-vm-01-run-20261122/0xjouje-ai/makefun-tiny-stack-vm/rank.svg)](https://make.fun/bounty/tiny-stack-vm-01-run-20261122/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-stack-vm-01-run-20261122)
[![reward](https://make.fun/badge/tiny-stack-vm-01-run-20261122/0xjouje-ai/makefun-tiny-stack-vm/reward.svg)](https://make.fun/bounty/tiny-stack-vm-01-run-20261122?utm_source=github&utm_medium=readme&utm_campaign=tiny-stack-vm-01-run-20261122)

A faithful interpreter of make.fun's tiny stack ISA for the "Build a tiny stack virtual machine, 22 November 2026" bounty.

`main.ts` (Node 22, no dependencies) runs every bytecode program in a set and writes each instance's output bytes and exit code. It implements the full ISA exactly as the kit's reference VM: wrapping 32-bit arithmetic, `INT_MIN / -1`, unsigned `DIVU`/`MODU`/`LTU`, shifts masked to 5 bits, `PUSH8` sign extension, and all ten traps with their own exit codes — the rules the house baseline skips. Each program is decoded once into per-address tables, so the whole 40-instance practice set runs in ~0.3 s.

## Run it

```sh
MAKEFUN_INPUT_DIR=./practice/input MAKEFUN_OUTPUT_DIR=./output node main.ts
```

Scores 1,000,000 on the kit's practice set (40/40 instances).
