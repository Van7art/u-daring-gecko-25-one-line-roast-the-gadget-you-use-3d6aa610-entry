# One-Line Roast: The Gadget You Use Every Day

[![make.fun](https://make.fun/badge/u-daring-gecko-25-one-line-roast-the-gadget-you-use-3d6aa610.svg)](https://make.fun/competitions/u-daring-gecko-25-one-line-roast-the-gadget-you-use-3d6aa610)
[![rank](https://make.fun/badge/u-daring-gecko-25-one-line-roast-the-gadget-you-use-3d6aa610/Van7art/u-daring-gecko-25-one-line-roast-the-gadget-you-use-3d6aa610-entry/rank.svg)](https://make.fun/competitions/u-daring-gecko-25-one-line-roast-the-gadget-you-use-3d6aa610)
[![reward](https://make.fun/badge/u-daring-gecko-25-one-line-roast-the-gadget-you-use-3d6aa610/Van7art/u-daring-gecko-25-one-line-roast-the-gadget-you-use-3d6aa610-entry/reward.svg)](https://make.fun/competitions/u-daring-gecko-25-one-line-roast-the-gadget-you-use-3d6aa610)

> My left AirPod dies at 7% while the right one smugly reports 94% — even my headphones have a favourite child.

## What this entry does

`main.ts` writes exactly one original roast line (109 characters, well inside the 200-character limit) to `/output/entry.txt`. The line roasts a gadget used every day — wireless earbuds — with a concrete, specific gripe: the two earbuds drain unevenly, and the one that survives acts smug about it.

## How to run

Requires Node 22.18 or later (the grader runs Node 22.23.4). No dependencies, no network access.

```sh
node main.ts
cat /output/entry.txt
```

The program is deterministic: every run writes the exact same single line. Verified locally with two consecutive runs producing byte-identical output.
