# Robotics_Final_Project
Robotics_Final_Project


File structure:

wall_e_ws/                      <-- Workspace
├── build/                      <-- colcon build
├── install/                    <-- colcon build
├── log/                        <-- Execute log
└── src/                        <-- Source code
    ├── wall_e_interfaces/      <-- [共用] 自定義訊息與服務定義
    │   ├── srv/
    │   │   └── GetTargetPose.srv  (定義請求/回應格式)
    │   ├── action/
    │   │   └── GraspTarget.action (定義抓取動作)
    │   ├── package.xml
    │   └── CMakeLists.txt
    │
    ├── wall_e_vision/          <-- Vision
    │   ├── wall_e_vision/      <-- Python source code
    │   │   ├── __init__.py
    │   │   ├── vision_node.py  (ROS 2 nodes)
    │   │   └── vision_utils.py (YOLO, PnP, get_valid_depth)
    │   ├── config/
    │   │   ├── K_matrix.npy
    │   │   └── D_coeffs.npy
    │   ├── models/
    │   │   └── wall-e-vision.pt (YOLO model)
    │   ├── package.xml
    │   └── setup.py
    │
    ├── wall_e_control/         <-- Control
    │   ├── wall_e_control/
    │   │   ├── __init__.py
    │   │   └── arm_controller_node.py (MoveIt! port)
    │   ├── package.xml
    │   └── setup.py
    │
    └── wall_e_integration/     <-- Navigation
        ├── wall_e_integration/
        │   ├── __init__.py
        │   └── coordinator_node.py <-- State machine
        ├── launch/
        │   └── main.launch.py  <-- Main launch file
        ├── maps/
        │   ├── lab_map.pgm
        │   └── lab_map.yaml
        ├── config/
        │   └── nav2_params.yaml
        ├── package.xml
        └── setup.py
