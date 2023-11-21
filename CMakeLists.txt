cmake_minimum_required(VERSION 3.5)
project(tiago_msgs)

# Default to C++14
if(NOT CMAKE_CXX_STANDARD)
  set(CMAKE_CXX_STANDARD 14)
endif()

# Find dependencies
find_package(ament_cmake REQUIRED)
find_package(rosidl_default_generators REQUIRED)
find_package(std_msgs REQUIRED)
find_package(action_msgs REQUIRED)
find_package(builtin_interfaces REQUIRED)

# Define message files
rosidl_generate_interfaces(${PROJECT_NAME}
  "msg/Command.msg"
  "msg/CaseInstance.msg"
  "msg/DynAgentDiag.msg"
  "msg/HazardObject.msg"
  "srv/DictionaryQuery.srv"
  "action/SaySentence.action"
  DEPENDENCIES std_msgs action_msgs builtin_interfaces
)

# Export dependencies
ament_export_dependencies(rosidl_default_runtime)
ament_package()

