set ( PROJECT_NAME SVM)
project ( ${PROJECT_NAME} )

cmake_minimum_required (VERSION 2.6)
#	add opencv libraries
FIND_PACKAGE( OpenCV REQUIRED )
IF (${OpenCV_VERSION} VERSION_LESS 2.3.1)
MESSAGE(FATAL_ERROR "OpenCV version is not compatible : ${OpenCV_VERSION}")
ENDIF()
#	add the executable
add_executable(${PROJECT_NAME} SVM.cpp)
#	add the libraries
TARGET_LINK_LIBRARIES( ${PROJECT_NAME} ${OpenCV_LIBS})