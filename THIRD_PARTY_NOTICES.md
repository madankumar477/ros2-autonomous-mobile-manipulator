# Third-Party Notices

## DOBOT ROS 2 V4 packages

The ME6 mesh package `cra_description` and the `dobot_rviz` dependency are not copied into this repository. They are imported through `dobot-dependencies.repos` from:

- https://github.com/Dobot-Arm/DOBOT_6Axis_ROS2_V4
- Pinned commit: `0f21e9839888f188ac06b0a9fea622d13a29a74f`
- The upstream repository includes its own `LICENSE` file and package-level attribution. Preserve those notices when importing or redistributing the vendor source.

## AWS RoboMaker warehouse world assets

The selected model folders under `src/edubot_description/models/aws_robomaker_warehouse_*` are used by `hall1demo.world`. They originate from AWS RoboMaker's small warehouse world:

- https://github.com/aws-robotics/aws-robomaker-small-warehouse-world
- ROS 2 branch: `ros2`
- Upstream license: MIT-0; a copy of the license text is provided in `licenses/AWS-RoboMaker-MIT-0.txt`.

Only the warehouse model directories referenced by the included `hall1demo.world` are retained.

## Original project package metadata

The original package maintainers and package-level license values from the supplied workspace were retained. In particular, some `edubot_*` manifests contain a `TODO: License declaration`, and `edubot_me6_moveit` declares BSD with DOBOT attribution. See `LICENSE_STATUS.md`; this repository does not silently replace those declarations with a new blanket license.
