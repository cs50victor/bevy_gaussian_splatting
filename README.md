# bevy_gaussian_splatting

[![test](https://github.com/mosure/bevy_gaussian_splatting/workflows/test/badge.svg)](https://github.com/Mosure/bevy_gaussian_splatting/actions?query=workflow%3Atest)
[![GitHub License](https://img.shields.io/github/license/mosure/bevy_gaussian_splatting)](https://raw.githubusercontent.com/mosure/bevy_gaussian_splatting/main/LICENSE)
[![GitHub Last Commit](https://img.shields.io/github/last-commit/mosure/bevy_gaussian_splatting)](https://github.com/mosure/bevy_gaussian_splatting)
[![GitHub Releases](https://img.shields.io/github/v/release/mosure/bevy_gaussian_splatting?include_prereleases&sort=semver)](https://github.com/mosure/bevy_gaussian_splatting/releases)
[![GitHub Issues](https://img.shields.io/github/issues/mosure/bevy_gaussian_splatting)](https://github.com/mosure/bevy_gaussian_splatting/issues)
[![Average time to resolve an issue](https://isitmaintained.com/badge/resolution/mosure/bevy_gaussian_splatting.svg)](http://isitmaintained.com/project/mosure/bevy_gaussian_splatting)
![crates.io](https://img.shields.io/crates/v/bevy_gaussian_splatting.svg)

![Alt text](docs/notferris.png)

bevy gaussian splatting render pipeline plugin

## capabilities

- [ ] bevy gaussian cloud render pipeline
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
        verticies: asset_server.load("scenes/test.ply"),
        ..Default::default()
    });

    commands.spawn(Camera3dBundle::default());
}
```


# credits

- [bevy](https://github.com/bevyengine/bevy)
- [gaussian-splatting](https://github.com/graphdeco-inria/gaussian-splatting)
- [diff-gaussian-rasterization](https://github.com/graphdeco-inria/diff-gaussian-rasterization)
- [rusty-automata](https://github.com/mosure/rusty-automata)
- [sturdy-dollop](https://github.com/mosure/sturdy-dollop)
