cmake_minimum_required(VERSION 3.9)
project(selfsign)

find_package(OpenSSL REQUIRED)

if(OPENSSL_FOUND)
set(OPENSSL_USE_STATIC_LIBS TRUE)
endif()

set(SOURCE_FILES "src/selfsign.cpp")
include_directories(${OPENSSL_INCLUDE_DIR})
add_executable(${PROJECT_NAME} ${SOURCE_FILES})
target_link_libraries(${PROJECT_NAME} ${OPENSSL_LIBRARIES} crypt32 ws2_32)
