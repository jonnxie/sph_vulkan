cmake_minimum_required(VERSION 3.17)
project(SPH)

set(CMAKE_CXX_STANDARD 20)

aux_source_directory(source/ INCLUDE)
aux_source_directory(source/*.cpp SOURCE)

set(DIR_INC ${INCLUDE})
set(DIR_SOU ${SOURCE})

add_executable(SPH ${DIR_INC} ${DIR_SOU} source/main.cpp)


## GLFW
set(GLFW_INCLUDE_DIRS C:/Users/maybe/Desktop/third-part-library/glfw-3.3.2.bin.WIN64/include/GLFW/)
set(GLFW_LIBRARIES C:/Users/maybe/Desktop/third-part-library/glfw-3.3.2.bin.WIN64/lib-mingw-w64/)
include_directories(${GLFW_INCLUDE_DIRS})
target_link_libraries(SPH ${GLFW_LIBRARIES})

target_link_libraries(SPH glfw3)

## GLM
set(GLM_INCLUDE_DIRS C:/VulkanSDK/1.2.154.1/Third-Party/Include/glm/)
include_directories(${GLM_INCLUDE_DIRS})

## VulKan
find_package(Vulkan REQUIRED)
target_include_directories(SPH PUBLIC ${Vulkan_INCLUDE_DIRS})
target_link_libraries(SPH ${Vulkan_LIBRARIES})



