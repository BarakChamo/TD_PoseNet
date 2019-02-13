# TouchDesign + PoseNet with [Runway](https://github.com/runwayml)
A PoseNet to TouchDesigner integration using [Runway ML](https://runwayapp.ai)

### What's PoseNet
[PoseNet](https://github.com/tensorflow/tfjs-models/tree/master/posenet) is a machine-learning based pose detection model built on [TensorFlow.js](https://js.tensorflow.org).

### What's Runway
[Runway](https://runwayapp.ai) is an intuitive machine learning tool for creators.

### What's this project
This project is a basic implementation of PoseNet in TouchDesigner via an OSC bridge to Runway.
It includes:

#### 1. PoseNet OSC tox
A tox external for communicating with Runway running PoseNet

#### 2. Example project
An example project showing how to use the pose data to outline a face, 
including calculations of face's distance from the camera.

### How to use the .tox
To use the .tox first load it into your project, make sure the OSC port and IP are correct and toggle `Enable OSC`,
this will send the initiation message to Runway and begin streaming detected pose data from the `DAT` output.

The output includes the overall pose score as we as a `_score`, `_x` and `_y` for every keypoint.

You can also
1. choose which keypoints to export (less keypoints improve performance).
2. Normalize pose coordinates to screen space (0 to 1) instead of absolute pixel position.

### How to setup a Runway environment with PoseNet over OSC.
1. Restore a workspace or start from a new model and choose `PoseNet`.
2. Set the output to `Network` and then `OSC` and verify the ip and port.
3. Hit `Run PoseNet`.
4. Toggle `Enable OSC` in TouchDesigner.
