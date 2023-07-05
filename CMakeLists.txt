cmake_minimum_required(VERSION 3.10)
project(sfgui_vendor)

find_package(ament_cmake_auto REQUIRED)
ament_auto_find_build_dependencies()

find_package(SFML COMPONENTS system window graphics REQUIRED)

ament_vendor(${PROJECT_NAME}
  SATISFIED ${sfgui_FOUND}
  VCS_URL https://github.com/TankOs/SFGUI.git
  VCS_VERSION 83471599284b2a23027b9ab4514684a6eeb08a19
  CMAKE_ARGS
    -DCMAKE_BUILD_TYPE=RelWithDebInfo
)

ament_auto_package()
