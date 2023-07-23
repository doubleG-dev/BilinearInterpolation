cmake_minimum_required(VERSION 3.0.0)
project(bilinProject VERSION 0.1.0 LANGUAGES C CXX)

include(CTest)
enable_testing()

set(OpenCV_DIR /home/doubleg/Documents/opencv450)
find_package(OpenCV REQUIRED PATHS ${OpenCV_DIR} NO_DEFAULT_PATH)

include_directories( ${OpenCV_INCLUDE_DIRS} )

add_executable(bilinProject main.cpp)

target_link_libraries(${PROJECT_NAME} ${OpenCV_LIBS})


set(CPACK_PROJECT_NAME ${PROJECT_NAME})
set(CPACK_PROJECT_VERSION ${PROJECT_VERSION})
include(CPack)
