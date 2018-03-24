cmake_minimum_required(VERSION 3.9)
project(selfsign)

find_package(OpenSSL REQUIRED)
if(OPENSSL_FOUND)
set(OPENSSL_USE_STATIC_LIBS TRUE)
endif()

set(SOURCES_FILES "src/selfsign.cpp")

add_executable(${PROJECT_NAME} ${SOURCES_FILES})
target_link_libraries(${PROJECT_NAME}  OpenSSL::Crypto)
