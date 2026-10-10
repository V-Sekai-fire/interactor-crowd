# interactor-crowd

A native crowd plane that simulates a venue of people and publishes each body joint as a fabric entity.

## What it is for

The fabric's entity packet holds one rotation, too little for an articulated body, so this plane gives every joint its own entity. It steers the crowd, solves contact between bodies in one MuJoCo model, and encodes entity packets for a separate edge process to send. Lean theorems in `spec/` state its time budget, and [docs/logbook](docs/logbook) holds the measurements behind them.

## Build and run

CMake needs `MUJOCO_ROOT` set to a MuJoCo install:

    cmake -S . -B build -DMUJOCO_ROOT=<mujoco>
    cmake --build build && ctest --test-dir build

The plane is `build/weft-crowd-plane`; the comment at the top of `src/plane.cpp` lists its arguments and environment.

## Licence

Apache-2.0. See [LICENSE](LICENSE).
