# bevy_gaussian_splatting 🌌

[![test](https://github.com/mosure/bevy_gaussian_splatting/workflows/test/badge.svg)](https://github.com/Mosure/bevy_gaussian_splatting/actions?query=workflow%3Atest)
[![GitHub License](https://img.shields.io/github/license/mosure/bevy_gaussian_splatting)](https://raw.githubusercontent.com/mosure/bevy_gaussian_splatting/main/LICENSE)
[![GitHub Last Commit](https://img.shields.io/github/last-commit/mosure/bevy_gaussian_splatting)](https://github.com/mosure/bevy_gaussian_splatting)
[![GitHub Releases](https://img.shields.io/github/v/release/mosure/bevy_gaussian_splatting?include_prereleases&sort=semver)](https://github.com/mosure/bevy_gaussian_splatting/releases)
[![GitHub Issues](https://img.shields.io/github/issues/mosure/bevy_gaussian_splatting)](https://github.com/mosure/bevy_gaussian_splatting/issues)
[![Average time to resolve an issue](https://isitmaintained.com/badge/resolution/mosure/bevy_gaussian_splatting.svg)](http://isitmaintained.com/project/mosure/bevy_gaussian_splatting)
[![crates.io](https://img.shields.io/crates/v/bevy_gaussian_splatting.svg)](https://crates.io/crates/bevy_gaussian_splatting)

bevy gaussian splatting render pipeline plugin. view the [live demo](https://mosure.github.io/bevy_gaussian_splatting/index.html?arg1=cactus.gcloud)

![Alt text](docs/bevy_gaussian_splatting_demo.webp)
![Alt text](docs/go.gif)


## capabilities

- [X] ply to gcloud converter
- [X] gcloud and ply asset loaders
- [X] bevy gaussian cloud render pipeline
- [X] gaussian cloud particle effects
- [X] wasm support /w [live demo](https://mosure.github.io/bevy_gaussian_splatting/index.html?arg1=cactus.gcloud)
- [X] depth colorization
- [X] f16 and f32 gcloud
- [X] wgl2 and webgpu
- [ ] spherical harmonic coefficients clustering
- [ ] 4D gaussian cloud wavelet compression
- [ ] accelerated spatial queries
- [ ] temporal depth sorting
- [ ] skeletons
- [ ] volume masks
- [ ] level of detail
- [ ] lighting and shadows
- [ ] bevy_openxr support
- [ ] bevy 3D camera to gaussian cloud pipeline

## usage

```rust
use bevy::prelude::*;
use bevy_gaussian_splatting::GaussianSplattingPlugin;

fn main() {
    App::build()
        .add_plugins(DefaultPlugins)
        .add_plugins(GaussianSplattingPlugin)
        .add_systems(Startup, setup_gaussian_cloud)
        .run();
}

fn setup_gaussian_cloud(
    mut commands: Commands,
    asset_server: Res<AssetServer>,
) {
    commands.spawn(GaussianSplattingBundle {
        cloud: asset_server.load("scenes/icecream.gcloud"),
        ..Default::default()
    });

    commands.spawn(Camera3dBundle::default());
}
```

## tools

- [ply to gcloud converter](tools/README.md#ply-to-gcloud-converter)
- [gaussian cloud training pipeline](https://github.com/mosure/burn_gaussian_splatting)
- aabb vs. obb gaussian comparison via `cargo run --bin compare_aabb_obb`


## compatible bevy versions

| `bevy_gaussian_splatting` | `bevy` |
| :--                       | :--    |
| `0.4 - 1.0`               | `0.12` |
| `0.1 - 0.3`               | `0.11` |

## projects using this plugin
- [kitt2](https://github.com/cs50victor/kitt2)

# credits

- [4d gaussians](https://github.com/hustvl/4DGaussians)
- [4d-gaussian-splatting](https://fudan-zvg.github.io/4d-gaussian-splatting/)
- [bevy](https://github.com/bevyengine/bevy)
- [bevy-hanabi](https://github.com/djeedai/bevy_hanabi)
- [d3ga](https://zielon.github.io/d3ga/)
- [deformable-3d-gaussians](https://github.com/ingra14m/Deformable-3D-Gaussians)
- [diff-gaussian-rasterization](https://github.com/graphdeco-inria/diff-gaussian-rasterization)
- [dreamgaussian](https://github.com/dreamgaussian/dreamgaussian)
- [dynamic-3d-gaussians](https://github.com/JonathonLuiten/Dynamic3DGaussians)
- [ewa splatting](https://www.cs.umd.edu/~zwicker/publications/EWASplatting-TVCG02.pdf)
- [gaussian-grouping](https://github.com/lkeab/gaussian-grouping)
- [gaussian-splatting](https://github.com/graphdeco-inria/gaussian-splatting)
- [gaussian-splatting-viewer](https://github.com/limacv/GaussianSplattingViewer/tree/main)
- [gaussian-splatting-web](https://github.com/cvlab-epfl/gaussian-splatting-web)
- [gir](https://3dgir.github.io/)
- [making gaussian splats smaller](https://aras-p.info/blog/2023/09/13/Making-Gaussian-Splats-smaller/)
- [masked-spacetime-hashing](https://github.com/masked-spacetime-hashing/msth)
- [onesweep](https://arxiv.org/ftp/arxiv/papers/2206/2206.01784.pdf)
- [pasture](https://github.com/Mortano/pasture)
- [phys-gaussian](https://xpandora.github.io/PhysGaussian/)
- [point-visualizer](https://github.com/mosure/point-visualizer)
- [rusty-automata](https://github.com/mosure/rusty-automata)
- [scaffold-gs](https://city-super.github.io/scaffold-gs/)
- [shader-one-sweep](https://github.com/b0nes164/ShaderOneSweep)
- [spacetime-gaussians](https://github.com/oppo-us-research/SpacetimeGaussians)
- [splat](https://github.com/antimatter15/splat)
- [splatter](https://github.com/Lichtso/splatter)
- [sturdy-dollop](https://github.com/mosure/sturdy-dollop)
- [sugar](https://github.com/Anttwo/SuGaR)
- [taichi_3d_gaussian_splatting](https://github.com/wanmeihuali/taichi_3d_gaussian_splatting)
