# Validation Notes and Known Issues

This document records facts observed in the uploaded `mobile_manipulator_ws.zip`. It is not a claim that the curated repository has been rebuilt and hardware-tested from a clean environment.

## What the archive contains as evidence

- The source tree contains a combined Xacro model joining the mobile chassis to the ME6 arm.
- A recorded TF tree contains `base_link`, `base_footprint`, `chassis`, sensor frames, `me6_base_link` and `me6_Link1` through `me6_Link6`.
- The archive also contains a separate diagnostic output reporting `No tf data received`.
- One recorded display launch log reports `link 'base_link' is not unique` and a failed `robot_state_publisher` initialization.
- The included combined MoveIt control Xacro uses `mock_components/GenericSystem`; it is a simulation/virtual controller configuration, not a physical arm driver.

## Publication cleanup

The curated repository excludes generated `build/`, `install/`, and `log/` content. It also excludes local expanded URDF dumps and stale absolute paths embedded in comments, old map/SLAM serialization files, duplicate configuration backups and unused world assets.

## Validation performed for this package

- Source files and package manifests were filtered by package role and referenced launch/model assets.
- XML/Xacro/package manifest parse checks and Python syntax checks are run on the curated files before packaging.
- The ROS 2 Humble `colcon` build and a physical robot acceptance test were not run in this packaging environment.

## Before using the workspace

1. Rebuild from a clean Ubuntu 22.04 + ROS 2 Humble environment.
2. Verify that the combined Xacro expands to a valid URDF with unique link names.
3. Confirm the transform tree continuously publishes for both the base and six-joint arm.
4. Confirm the Gazebo plugins and `ros2_control` controllers load successfully.
5. Align the Nav2 map with the selected Gazebo world and verify localization/navigation.
6. Treat physical ME6 control as a separate integration task; the included MoveIt fake system will not operate the actual robot.
7. Verify the target robot's physical emergency-stop and downstream safety mechanisms before any hardware motion.
