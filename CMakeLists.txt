cmake_minimum_required(VERSION 3.10)

# Set the project name and version
project(EvilRobotGame VERSION 1.0)

include_directories(
	${PROJECT_SOURCE_DIR}/include
	${PROJECT_SOURCE_DIR}/src
)

# Set the C++ standard to use
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED True)

# Find the SDL2 library
#find_package(SDL2 REQUIRED)

file(GLOB SRCS
	"${PROJECT_SOURCE_DIR}/include/*"
	"${PROJECT_SOURCE_DIR}/src/*"
)

# Add the executable target
add_executable(EvilRobotGame ${SRCS})

# Link against the SDL2 library
#target_link_libraries(EvilRobotGame SDL2)

# Set the output directory for the executable
#set_target_properties(EvilRobotGame PROPERTIES RUNTIME_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/bin)

find_package(SDL2 REQUIRED)
target_link_libraries(EvilRobotGame ${SDL2_LIBRARIES})