project(baidudisk)

add_executable(baidudisk cache.cpp net.c urlcode.c json_object_from_file.c baiduapi.c threadpool.cpp main.c)

install(TARGETS baidudisk RUNTIME DESTINATION bin)

set(CMAKE_C_FLAGS "-D_FILE_OFFSET_BITS=64 -Wall -g")
set(CMAKE_CXX_FLAGS "-D_FILE_OFFSET_BITS=64 -std=c++11 -Wall -g")
set(CMAKE_EXE_LINKER_FLAGS "-ljson -lfuse -lssl -lcrypto -lpthread -lcurl")
