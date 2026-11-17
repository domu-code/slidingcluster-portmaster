# Sliding Cluster Puzzle / PortMaster

Native C++/SDL2 version of Sliding Cluster Puzzle, using PocketTracker 3 R8's Plaits, Rings and Handpan DSP.

## Current development build: Match Clarity + PocketTracker font

The complete game source and nine visual families are prepared, but **the ARM64 installer is not yet compiled or handheld-tested**.

The current fixes are:

- Dominant full-tile match colours and a stable **1-8 match identity badge**
- Small, clearly identified **B/P/S** special glyphs. Special blocks match by their underlying numbered colour
- Actual **quinine_five** bitmap glyphs from PocketTracker 3 R8's native `ui/font5x5.h`
- Correct shifter clear order: clear the original matching tiles **before** rotating the surrounding survivors
- Fixed grey tiles and portals are protected from bomb blasts
- All nine art themes, manual strips, edge-push spawn, wraparound and 40 curated modes retained

## Build the current PortMaster installer

1. Get `SlidingCluster_PT3_MatchClarity_Source.zip` from the ChatGPT build kit.
2. Upload that ZIP **unchanged** to the root of this repository using [Upload files](https://github.com/domu-code/slidingcluster-portmaster/upload/main).
3. Committing the upload triggers the [ARM64 build workflow](.github/workflows/build-slidingcluster-pt3.yml). The workflow verifies the source SHA-256, builds in an ARM64 Ubuntu 20.04 container, runs game and audio tests, and packages the compiled executable.
4. After a successful run, download the Actions artifact. The **inner** `slidingcluster_pt3.zip` is the PortMaster installable game archive.

The GitHub workflow cannot build until the corrected source ZIP has been uploaded to the repository.

## Testing

Local native rules tests, the 40-mode catalogue, and SDL2 UI syntax checks pass. Full Processing + Beads runtime validation, actual ARM64 compilation, and physical handheld tests are still pending.

The PocketTracker repositories are independent and have not been modified.
