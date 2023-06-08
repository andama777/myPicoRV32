# riscv-gnu-toolchainを使ってc言語プロジェクトをコンパイルするCMakeLists.txt

cmake_minimum_required(VERSION 3.13)

# プロジェクト名
project(RV32 C)

# バージョン番号
set(VERSION_MAJOR 1)
set(VERSION_MINOR 0)
set(VERSION_PATCH 0)

# ビルドタイプ
set(CMAKE_BUILD_TYPE Debug)

# ビルドオプション


# コンパイラ
set(CMAKE_C_COMPILER riscv32-unknown-elf-gcc)
set(CMAKE_CXX_COMPILER riscv32-unknown-elf-g++)
set(CMAKE_ASM_COMPILER riscv32-unknown-elf-gcc)

# ライブラリフォルダの指定 src/lib
set(LIBRARY_DIR ${CMAKE_CURRENT_SOURCE_DIR}/src/lib)

# ライブラリの指定
set(mylib ${LIBRARY_DIR}/mylib.c)

# ライブラリのインクルードディレクトリの指定
include_directories(${LIBRARY_DIR})

# ライブラリの追加
add_library(mylib STATIC ${mylib})

# ターゲットの指定
add_executable(main src/main.c)

# リンクするライブラリの指定
target_link_libraries(main mylib)