# Package Inventory

| Package | Role in this repository | Source status |
|---|---|---|
| `edubot_description` | Mobile-base URDF/Xacro, meshes, Gazebo world/assets and RViz configurations | Project workspace package; TODO license metadata retained |
| `edubot_controller` | Drive/controller, Gazebo bridge, SLAM Toolbox and Nav2 parameters; selected map pair | Project workspace package; TODO license metadata retained |
| `edubot_bringup` | Simulation, base, camera, mapping, localization and Nav2 launch files | Project workspace package; TODO license metadata retained |
| `edubot_me6_description` | Combined base + ME6 robot description, mount, simulation control Xacro | Package declares MIT; original package attribution retained |
| `edubot_me6_moveit` | Combined robot ME6 MoveIt planning and controller configuration | Package metadata declares BSD and attributes generated package to DOBOT; retained unchanged |

## Dependencies kept external

`cra_description`, `dobot_rviz` and the related vendor packages are fetched from the official DOBOT ROS 2 V4 repository using `dobot-dependencies.repos`. `dobot_moveit`, `dobot_msgs_v4` and standalone `me6_moveit` are not duplicated in this project repository; they are available through the upstream dependency import if needed by that stack.

## Deliberately excluded from the upload

- Colcon generated `build/`, `install/`, and `log/` directories.
- Duplicate standalone `me6_moveit` snapshot and `config_backup` copy.
- Stale pre-mesh-fix/original Xacro backups.
- Historical Cartographer `.data` and `.posegraph` files.
- Maps not referenced by the included Nav2 launch.
- Unused Gazebo worlds/models and sample model-reference photographs.
- Root-level expanded URDF dump, build logs and local TF diagnostic PDFs.
- `.DS_Store`, `.psd`, Python bytecode and temporary/cache files.
