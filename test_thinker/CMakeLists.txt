cmake_minimum_required(VERSION 3.20)

# # ADD_EXECTION(test_thinker ${CMAKE_CURRENT_SOURCE_DIR} ${ROOT_BIN_DIR})
# set(BEGIN_WHOLE_ARCHIVE -Wl,--whole-archive)
# set(END_WHOLE_ARCHIVE -Wl,--no-whole-archive)

# set(CPP_EXAMPLE_LIBS ${BEGIN_WHOLE_ARCHIVE} thinker m ${END_WHOLE_ARCHIVE})

# TARGET_LINK_LIBRARIES(test_thinker ${CPP_EXAMPLE_LIBS})

project(test_thinker VERSION 0.1.0 LANGUAGES C)

set(EXECUTABLE_OUTPUT_PATH ${PROJECT_BINARY_DIR}/bin)
set(SRCLIST 
    test_thinker.c
)

include_directories(./)
include_directories(/home/listenai/Develop/Listenai/LNN/thinker/thinker/executor/include)

add_executable(${PROJECT_NAME} ${SRCLIST})
link_directories(/home/listenai/Develop/Listenai/LNN/Listenai_Models/YOLOv1_QRcode_Detection/test_thinker)
# export LD_LIBRARY_PATH=/home/listenai/Develop/Listenai/LNN/Listenai_Models/YOLOv1_QRcode_Detection/test_thinker:$LD_LIBRARY_PATH
# target_link_libraries(${PROJECT_NAME} m)
target_link_libraries(${PROJECT_NAME} PRIVATE m thinker)