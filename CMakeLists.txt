cmake_minimum_required(VERSION 2.6)
project(seamsEasy)

set(CMAKE_BUILD_TYPE Release)
set(CMAKE_MODULE_PATH ${CMAKE_CURRENT_SOURCE_DIR}/../cmake_modules)

set(SOURCE_FILES
	"SeamsEasyCmd.h"
	"SeamsEasyCmd.cpp"
	"SeamsEasyNode.h"
	"SeamsEasyNode.cpp"
	"StitchEasyCmd.h"
	"StitchEasyCmd.cpp"
	"StitchEasyCtx.h"
	"StitchEasyCtx.cpp"
	"StitchEasyCtxCmd.h"
	"StitchEasyCtxCmd.cpp"
	"StitchEasyNode.h"
	"StitchEasyNode.cpp"
	"PluginMain.cpp"
	"../_library/SEdgeLoop.h"
	"../_library/SEdgeLoop.cpp"
	"../_library/SMesh.h"
	"../_library/SMesh.cpp"
	"../_library/SNode.h"
	"../_library/SSeamMesh.h"
	"../_library/SSeamMesh.cpp"
)

find_package(Maya REQUIRED)

include_directories(${MAYA_INCLUDE_DIR})
link_directories(${MAYA_LIBRARY_DIR})

add_library(${PROJECT_NAME} SHARED ${SOURCE_FILES})
target_link_libraries(${PROJECT_NAME} ${MAYA_LIBRARIES})

MAYA_PLUGIN(${PROJECT_NAME})