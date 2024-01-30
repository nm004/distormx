cmake_minimum_required(VERSION 3.20)
project(distromx LANGUAGES C)
add_library(distorm3 distorm3/src/decoder.c
		     distorm3/src/distorm.c
		     distorm3/src/instructions.c
		     distorm3/src/insts.c
		     distorm3/src/mnemonics.c
		     distorm3/src/operands.c
		     distorm3/src/prefix.c
		     distorm3/src/textdefs.c)
target_include_directories(distorm3 PUBLIC ${PROJECT_SOURCE_DIR}/distorm3/include)

add_library(distormx src/distormx.c
		     src/OS.c)
target_include_directories(distormx PUBLIC ${PROJECT_SOURCE_DIR}/include)
target_link_libraries(distormx distorm3)
