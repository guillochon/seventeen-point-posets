# Seventeen-Point Posets — OEIS A000112 and A000608

**https://guillochon.github.io/seventeen-point-posets/**

[A000112](https://oeis.org/A000112) counts partially ordered sets on n unlabeled points; the OEIS stopped at
a(16) = 4483130665195087 (Brinkmann and McKay, 2002). Burnside's lemma over the labeled counts
[A001035](https://oeis.org/A001035) gives

    a(17) = 378180373015320248,

and with it the connected count [A000608](https://oeis.org/A000608)(17) = 373626005846478701. The derivation, every
check, the programs and the logs are in
[oeis-results/A000112](https://github.com/guillochon/oeis-results/tree/main/A000112).

The page has three parts:

- **How symmetry counts posets.** For N = 3..6, every cycle type of the permutations of N points with its number of
  fixed posets, computed by the quotient theorem and checked by brute force over every labeled poset in the browser.
  Click a cycle type to step through its fixed posets, drawn with one color per cycle beside their quotient on the
  cycles and the offset sets between them.
- **Where a(n) comes from.** For n = 3..17, the share of the Burnside sum that is not a known labeled count, split by
  the number of interacting cycles. It falls to 0.66% at n = 17.
- **Every poset up to seven points.** All 2450 Hasse diagrams for n = 1..7, connected ones solid and disconnected
  ones dashed, with their symmetry counts; filter and sort.

## How it works

Everything runs in the browser, in one file (`index.html`).

- **Explainer.** Labeled posets are built point by point (a new point gets a down-set and an up-set), the fixed posets
  of a permutation are filtered from them, and the quotient count sums the valid offset sets over labeled posets on
  the cycles.
- **Gallery.** The Hasse diagrams come from nauty's `genposetg`; layers by longest chain, order by barycenter sweeps.
- **Chart.** The shares come from the per-class Burnside run (`burnside 17`) in the oeis-results folder.

Made by James Guillochon with Claude. The source lives in the oeis-sniper project (`viz/A000112/`); this repo holds
the published copy.
