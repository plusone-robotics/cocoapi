COCO API - http://cocodataset.org/

COCO is a large image dataset designed for object detection, segmentation, person keypoints detection, stuff segmentation, and caption generation. This package provides Matlab, Python, and Lua APIs that assists in loading, parsing, and visualizing the annotations in COCO. Please visit http://cocodataset.org/ for more information on COCO, including for the data, paper, and tutorials. The exact format of the annotations is also described on the COCO website. The Matlab and Python APIs are complete, the Lua API provides only basic functionality.

In addition to this API, please download both the COCO images and annotations in order to run the demos and use the API. Both are available on the project website.
-Please download, unzip, and place the images in: coco/images/
-Please download and place the annotations in: coco/annotations/
For substantially more details on the API please see http://cocodataset.org/#download.

After downloading the images and annotations, run the Matlab, Python, or Lua demos for example usage.

To install:
-For Matlab, add coco/MatlabApi to the Matlab path (OSX/Linux binaries provided)
-For Python, run "make" under coco/PythonAPI
-For Lua, run “luarocks make LuaAPI/rocks/coco-scm-1.rockspec” under coco/
-For c++ ROS catkin package, see below

Build and usage with ROS packages (using catkin as an example):
- Add this repo to your workspace
- For a package that needs to use "cocoapi" (say "user_pkg") assign cocoapi as a dependency:
  - set "<depend>cocoapi</depend>" in the "package.xml" for the "user_pkg"
  - in your "CMakeLists.txt" for "user_pkg" set "find_package(catkin REQUIRED COMPONENTS cocoapi)"
  - in your "CMakeLists.txt" for "user_pkg" set "catkin_package(... CATKIN_DEPENDS cocoapi)"
  - in your "CMakeLists.txt" for "user_pkg" setting "include_directories(${catkin_INCLUDE_DIRS})" allows finding the headers
  - in your "CMakeLists.txt" for "user_pkg" setting "target_link_libraries(... ${catkin_LIBRARIES})" allows linking the shared library for "cocoapi"
- You may include the corresponding header in your sources with either `extern "C" { #include <cocoapi/maskApi.h> }` or `#include <cocoapi/maskApi.h>` depending on weather your application code is in 'c' or 'c++'
- All methods and structs defined in the header may now be used in your source code