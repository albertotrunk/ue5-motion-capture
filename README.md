# UE 5.1 Build

![image](https://user-images.githubusercontent.com/8300565/221344546-54c6f04b-45a6-45b0-acd0-1b1244b54ebd.png)


# UE5 MediaPipe plugin

WARNING: this project is experimental and recommended for experienced developers only!

Platforms: UE 5.1  (Windows ONLY, other will not be supported)

2D features: Face, Iris, Hands, Pose, Holistic

3D features: Face Mesh, World Pose

Demo video: https://www.youtube.com/watch?v=_gRGjGn6FQE

## (Optional) Building the plugin and MediaPipe wrapper library

### Clone plugin

`git clone https://github.com/wongfei/ue4-mediapipe-plugin.git`

### Clone wrapper

`git clone -b unreal https://github.com/albertotrunk/mediapipe.git ue5-motion-capture`

[Setup workspace](https://google.github.io/mediapipe/getting_started/install.html)

### Build wrapper

`cd ue5-motion-capture`

`bazel build -c opt --define MEDIAPIPE_DISABLE_GPU=1 --action_env PYTHON_BIN_PATH="C:\\Python39\\python.exe" mediapipe/unreal:ump_shared`

See: `ue5-motion-capture\mediapipe\unreal\scripts\build_shared.cmd`

Copy ump_shared.dll to `ue4-mediapipe-plugin\Plugins\MediaPipe\ThirdParty\mediapipe\Binaries\Win64\`

See: `ue5-motion-capture\mediapipe\unreal\scripts\deploy.cmd`

### Other deps

Protobuf 3.11.4

Copy libprotobuf.lib to `ue4-mediapipe-plugin\Plugins\MediaPipe\ThirdParty\protobuf\Lib\Win64\`

(Optional) OpenCV 3.4.10 with fixed CAP_MSMF

`git clone -b msmf_fix_3410 https://github.com/wongfei/opencv.git`

Copy opencv_world3410.dll to `ue5-motion-capture\Plugins\MediaPipe\ThirdParty\mediapipe\Binaries\Win64\`
