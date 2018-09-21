# pseudofractals-voxel-shader

Voxel shader (for [MagicaVoxel](https://ephtracy.github.io/)) to generate pseudofractal volumes.

## Installing and updating

Copy the files in `shaders` to the `shader` in your installation of MagicaVoxel.

## Usage

In MagicaVoxel, execute **xs pseudofractal 1 1 1 2 1.33 0.5** in its console.

## Parameters

``xs pseudofractal xscale yscale zscale distOrder seed threshold cleaning``

- **xscale :** The scale on the X axis. Small number stretches the axis, large number condenses it.
- **yscale :** The scale on the Y axis. Small number stretches the axis, large number condenses it.
- **zscale :** The scale on the Z axis. Small number stretches the axis, large number condenses it.
- **distOrder :** The algorithm uses [Minkowski distance](https://en.wikipedia.org/wiki/Minkowski_distance) which is a generalization of Euclidean and Manhattan distance. Values larger than 2 tend to result in squarish structure with flat surfaces. Values very close to 1 (i.e. 1.0001) tend to result in regular octahedra. Recommended values are between 0.5 and 2.
- **seed :** The "magic" value used to generate the pseudofractal. To be specific it is used as a modulus. A value of 1 or 0 will always result in an empty volume.
- **threshold :** A value of 0 means that all voxels are considered as dead. A value of 1 means that all voxels are considered as alive.
- **cleaning :** If set and above 0, single / isolated voxels will be removed from the resulting volume.

## Recommended workflow

 * Start with the scales set to 1, distOrder set to 2. or 1.0001, seed set to a number other than 1 and 0, threshold sets to 0.5
 * Tweak the scales, distOrder and seed until you have an interesting volume.
 * Fine tune the threshold and eventually enable orphanRemoval if there too many isolated voxels.

## Additionnal notes

 * [Alien](https://twitter.com/LienTheAlien) is the one who first introduced me to pseudofractals, so thank to him.
 * Check Jes Wolfe's talk on the subject ([youtube](https://t.co/NcJOgdn0bu)) if you want to learne more about pseudofractals.
 * If you're interested in this kind of structure but want something more predictable and less random, check [cellular-automata-voxel-shader](https://github.com/kchapelier/cellular-automata-voxel-shader).