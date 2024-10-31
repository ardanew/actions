cmake_minimum_required(VERSION 3.23...3.24)
project(actions LANGUAGES CXX)

set(TARGET_NAME "actions")

add_executable(${TARGET_NAME})

target_sources(${TARGET_NAME} PRIVATE
    main.cpp
)

if(BUILD_TESTS)
#    add_subdirectory(tests)
endif(BUILD_TESTS)

include(GNUInstallDirs)
install(
    TARGETS ${TARGET_NAME}
    EXPORT ${PROJECT_NAME}
    PERMISSIONS OWNER_WRITE OWNER_READ
    RUNTIME DESTINATION ${CMAKE_INSTALL_PREFIX}
)
