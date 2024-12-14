project(yolo11ncnn)

cmake_minimum_required(VERSION 3.4.1)

set(OpenCV_DIR ${CMAKE_SOURCE_DIR}/opencv-mobile-4.10.0-android/sdk/native/jni)
find_package(OpenCV REQUIRED core imgproc)

set(ncnn_DIR ${CMAKE_SOURCE_DIR}/ncnn-20240820-android-vulkan/${ANDROID_ABI}/lib/cmake/ncnn)
find_package(ncnn REQUIRED)

add_library(yolo11ncnn SHARED yolo11ncnn_jni.cpp)

target_link_libraries(yolo11ncnn
    ncnn
    ${OpenCV_LIBS}
    jnigraphics
)
