CMAKE_MINIMUM_REQUIRED(VERSION 2.8)

SET(EXECUTABLE_OUTPUT_PATH "${PROJECT_BINARY_DIR}/bin")
MESSAGE(STATUS "bin out path: ${EXECUTABLE_OUTPUT_PATH}")

AUX_SOURCE_DIRECTORY(${PROJECT_SOURCE_DIR}/libthreadpool/example THREADPOOL_EXAMPLE_SRC)
INCLUDE_DIRECTORIES("${PROJECT_SOURCE_DIR}/libthreadpool/include")
LINK_DIRECTORIES("${PROJECT_BINARY_DIR}/lib")

ADD_EXECUTABLE(threadpool_example ${THREADPOOL_EXAMPLE_SRC})
TARGET_LINK_LIBRARIES(threadpool_example libthreadpool.a)
