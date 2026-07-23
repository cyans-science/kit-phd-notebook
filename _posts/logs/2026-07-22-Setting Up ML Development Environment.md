---
title: "Setting Up ML Development Environment"
date: 2026-07-22
# summary: "Initial note on setting up a research log habit for PhD work."
tags: [research-log, phd, writing]
---

<!-- ## Question -->
<!-- What kind of research note system should support my PhD work over the next three years? -->

## Context
I am taking over from my predecessor researcher, Dr. Alessandro Brusamolino. I am trying to figure out the overall data pipeline structure, as well as to train with the most basic configuration. I found out a simple training takes several hours, so my plan is to make ML experiments much simpler and faster, enabling agile development.

## What I did
1. Made a DJC datacollection with a single root file in the data directory. I used Alessandro's manual and try to do it by myself. There were some sourcing issues, but eventually got the `convertDJCFromSource` command working.
2. I read the existing training script and batching script, installing packages and libraries I need.
   1. ~~Install miniforge3 to install Miniconda~~
   2. ~~Setup conda environment~~
   3. ~~Setup DJC data~~
   4. ~~Modify the batching script~~
3. Realised setups in 1 are not compatible with current docker containerisation and wandb api keys.
   1. Reverted back to the original design and decided to keep it
   2. Provided my wandb key
   3. Change these:
      * input file name: use the small one
      * True the --wandb flag in `topas_submit.py`
   4. Q: The exact role of Docker? To provide an identical and stable ground for development/execution?
4. Realised `ceph` is for storaging of big files ad should do development in `work`
   * Let's start all over: setup git, clone e2ereco, clone DJC, ~~covert small size files~~ (this should be put in `ceph` and I already have them), setup wandb (training script), configure training script accordingly
     * the submit python script (`topas_submit.py`) from the e2ereco repository doesn't work as it is. I used Alessandro's script, and it does. 
       * TODO: need to compare to check what is the discrepancy and why one worked and the other didn't

<!-- ## What I did

I started setting up a GitHub Pages blog with separate sections for research logs, paper notes, and rewritten paragraphs. -->
<!-- 
## Interpretation

The research log should remain functional and lightweight. It should not become a polished essay every day. -->
<!-- 
## Next action

Create the first paper-note template and decide the minimum structure for weekly notes. -->