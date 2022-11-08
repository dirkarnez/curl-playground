cmake_minimum_required(VERSION 3.14)

project(curl-playground)

find_package(CURL REQUIRED) 
if (CURL_FOUND)
    message("CURL found")
else (CURL_FOUND)
    message("CURL not found")
endif()

SET(CMAKE_EXE_LINKER_FLAGS "${CMAKE_EXE_LINKER_FLAGS} -static")

add_executable(${PROJECT_NAME}
    "src/main.cpp"
)

target_link_libraries(${PROJECT_NAME} CURL::libcurl)