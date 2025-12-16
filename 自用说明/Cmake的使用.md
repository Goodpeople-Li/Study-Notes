cmake_minimum_required(VERSION 3.16)

# =============================================================================
# 1. 交叉编译工具链配置 (Cross-Compilation Toolchain Setup)
# =============================================================================
# 设置目标系统为 Linux
set(CMAKE_SYSTEM_NAME Linux)
# 设置目标处理器架构为 loongarch64
set(CMAKE_SYSTEM_PROCESSOR loongarch64)

# 指定 C 语言交叉编译器路径
set(CMAKE_C_COMPILER "/opt/loongson-toolchain/loongson-gnu-toolchain-8.3-x86_64-loongarch64-linux-gnu-rc1.3-1/bin/loongarch64-linux-gnu-gcc")
# 指定 C++ 语言交叉编译器路径
set(CMAKE_CXX_COMPILER "/opt/loongson-toolchain/loongson-gnu-toolchain-8.3-x86_64-loongarch64-linux-gnu-rc1.3-1/bin/loongarch64-linux-gnu-g++")

# [可选] 指定静态库索引工具 (通常 CMake 会自动找到，特殊情况可手动指定)
# set(CMAKE_AR "/opt/loongson-toolchain/.../bin/loongarch64-linux-gnu-ar")
# set(CMAKE_RANLIB "/opt/loongson-toolchain/.../bin/loongarch64-linux-gnu-ranlib")

# =============================================================================
# 2. 项目基本信息 (Project Information)
# =============================================================================
# 定义项目名称及支持的语言 (C 和 C++)
project(main)

# [可选] 自动查找 src 目录下所有的源文件并保存到 SRC 变量中
# file(GLOB SRC ${PROJECT_SOURCE_DIR}/src/*.cpp ${PROJECT_SOURCE_DIR}/src/*.c)

# =============================================================================
# 3. 依赖库配置 (Dependencies Configuration)
# =============================================================================

# --- OpenCV 配置 ---
# 指定 OpenCV 的安装路径 (OpenCVConfig.cmake 所在的目录)
set(OpenCV_DIR "/home/goodpeople/loongarch_libs/opencv/install/lib/cmake/opencv4")

# 查找 OpenCV 库，REQUIRED 表示如果找不到则报错停止
find_package(OpenCV REQUIRED)

# 打印 OpenCV 的状态信息，用于调试路径是否正确
message(STATUS "OpenCV library status:")
message(STATUS "    version: ${OpenCV_VERSION}")
message(STATUS "    include path: ${OpenCV_INCLUDE_DIRS}")
message(STATUS "    libraries: ${OpenCV_LIBS}")

# [备用方案] 如果 find_package 不可用，可以使用 find_library 手动查找库文件
# include_directories(/path/to/opencv/include)
# find_library(OpenCV_CORE      opencv_core      PATHS /path/to/opencv/lib)
# find_library(OpenCV_IMGPROC   opencv_imgproc   PATHS /path/to/opencv/lib)
# find_library(OpenCV_HIGHGUI   opencv_highgui   PATHS /path/to/opencv/lib)
# find_library(OpenCV_VIDEOIO   opencv_videoio   PATHS /path/to/opencv/lib)
# find_library(OpenCV_IMGCODECS opencv_imgcodecs PATHS /path/to/opencv/lib)

# =============================================================================
# 4. 头文件路径 (Include Directories)
# =============================================================================
# 包含 OpenCV 的头文件目录
include_directories(${OpenCV_INCLUDE_DIRS})

# [可选] 包含项目自身的头文件目录 (例如 include 文件夹)
# include_directories(${PROJECT_SOURCE_DIR}/include)

# [可选] 包含交叉编译链的系统头文件 (通常编译器会自动处理，除非有特殊需求)
# include_directories(/opt/loongson-toolchain/.../include)

# =============================================================================
# 5. 库文件路径 (Library Directories)
# =============================================================================
# [可选] 手动指定库文件搜索路径 (find_package 通常会自动处理，手动链接时可能需要)
# link_directories(/path/to/opencv/lib)

# =============================================================================
# 6. 生成目标 (Build Targets)
# =============================================================================
# 生成可执行文件 main
# 如果有多个源文件，可以在后面继续添加，例如: add_executable(main main.c utils.c)
# 或者使用变量: add_executable(main ${SRC})
add_executable(main main.c)

# =============================================================================
# 7. 链接库 (Link Libraries)
# =============================================================================
# 将 OpenCV 库链接到可执行文件
# ${OpenCV_LIBS} 包含了所有找到的 OpenCV 模块，无需一个个列出
target_link_libraries(main PUBLIC ${OpenCV_LIBS})

# 链接 pthread 线程库 (Linux 下通常需要)
target_link_libraries(main PUBLIC pthread)

# [备用方案] 如果手动查找库，则需要一个个链接
# target_link_libraries(main PUBLIC ${OpenCV_CORE} ${OpenCV_IMGPROC} ...)

