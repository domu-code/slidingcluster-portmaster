# Sliding Cluster Puzzle / PortMaster

Native C++/SDL2 handheld port of Sliding Cluster Puzzle, sharing the Plaits, Rings and Handpan synthesis engines with PocketTracker 3.

## Status

The **ARM64 build workflow is configured**, but no installable binary has been produced or verified yet. Source archive upload and an ARM64 build are still required.

## Build the corrected edition

1. Upload **`SlidingCluster_PT3_AllThemes_FixedSource.zip`** to the root of this repository, unchanged.
2. The [ARM64 workflow](.github/workflows/build-slidingcluster-pt3.yml) starts automatically when the upload is committed. It can also be launched using **Actions → Build Sliding Cluster All Themes (PortMaster ARM64) → Run workflow**.
3. After a successful build, download the `SlidingCluster-PortMaster-ARM64-...` Actions artifact.
4. Unzip the Actions artifact once. The inner `slidingcluster_pt3.zip` is the PortMaster installation archive.
5. Copy `slidingcluster_pt3.zip` into your SD card's PortMaster autoinstall folder, or extract its contents beneath `roms/ports`.

## Current fixes

- Nine theme atlases with correct 32×32 tile boundaries
- Six theme families rebuilt with dedicated pixel artwork rather than unreliable poster crops; Neon Arcade likewise redrawn, Signal Terminal source art retained
- Stronger colour-identity markers so same-colour matches are legible
- Fixed grey blocks are visually distinguished from movable grey blocks
- Manual row/column shifts and 3×3 shifter rotations refuse to move immovable blocks or portals
- All 40 curated gameplay modes retained

## Validation

Local C++ rules checks pass, including edge wraparound tests and fixed-block strip invariants. 40 curated preset checks pass. The SDL2 final compile and physical handheld tests have not been completed.

The PocketTracker 3 repositories are unrelated to this release and are not modified.
