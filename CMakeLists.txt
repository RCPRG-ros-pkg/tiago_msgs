cmake_minimum_required(VERSION 2.8.3)
project(tiago_msgs)

find_package(catkin REQUIRED COMPONENTS message_generation actionlib_msgs)

add_message_files(
  DIRECTORY msg
  FILES
  Command.msg
  CaseInstance.msg
  DynAgentDiag.msg
  HazardObject.msg
)

add_service_files(
  FILES
  DictionaryQuery.srv
)

add_action_files(DIRECTORY action FILES SaySentence.action)

generate_messages(DEPENDENCIES actionlib_msgs)

catkin_package(
  CATKIN_DEPENDS message_runtime)

