# Copyright Xstrahl, Inc
cmake_minimum_required(VERSION 3.11 FATAL_ERROR)

project(InterviewTest)

find_package(Qt5 COMPONENTS Core Gui Widgets)

set(CMAKE_INCLUDE_CURRENT_DIR ON)

set(project_sources 
	src/main.cpp
	src/mainwindow.cpp)

set(project_headers
	src/mainwindow.h)

set(project_ui 
	ui/mainwindow.ui)

qt5_wrap_cpp(project_headers_moc ${project_headers})
qt5_wrap_ui(project_form_headers ${project_ui})

add_executable(${PROJECT_NAME} ${project_sources} ${project_headers} ${project_headers_moc} ${project_form_headers})
target_link_libraries(${PROJECT_NAME}
	Qt5::Core
	Qt5::Widgets
	Qt5::Gui
)

add_custom_command(TARGET InterviewTest POST_BUILD
	COMMAND ${CMAKE_COMMAND} -E copy_if_different $<TARGET_FILE:Qt5::Core> $<TARGET_FILE_DIR:InterviewTest>
	COMMAND ${CMAKE_COMMAND} -E copy_if_different $<TARGET_FILE:Qt5::Gui> $<TARGET_FILE_DIR:InterviewTest>
	COMMAND ${CMAKE_COMMAND} -E copy_if_different $<TARGET_FILE:Qt5::Widgets> $<TARGET_FILE_DIR:InterviewTest>
)
