cmake_minimum_required(VERSION 3.16)
project(umka_lang)

set(CMAKE_CXX_STANDARD 11)
set(SOURCE_DIR ${PROJECT_SOURCE_DIR}/src)

include_directories(${SOURCE_DIR})

add_library(umka STATIC
        ${SOURCE_DIR}/umka_api.c
        ${SOURCE_DIR}/umka_common.c
        ${SOURCE_DIR}/umka_compiler.c
        ${SOURCE_DIR}/umka_const.c
        ${SOURCE_DIR}/umka_decl.c
        ${SOURCE_DIR}/umka_expr.c
        ${SOURCE_DIR}/umka_gen.c
        ${SOURCE_DIR}/umka_ident.c
        ${SOURCE_DIR}/umka_lexer.c
        ${SOURCE_DIR}/umka_runtime.c
        ${SOURCE_DIR}/umka_stmt.c
        ${SOURCE_DIR}/umka_types.c
        ${SOURCE_DIR}/umka_vm.c)
add_executable(umka-cli
        ${SOURCE_DIR}/umka.c)
target_link_libraries(umka-cli umka m)
#add_subdirectory(exec)
#add_subdirectory(lib)

