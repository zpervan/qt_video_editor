project(Backend_Lib)

set(HEADERS
        thumbnail_creator.h
        path_creator.h
        random_generator.h
        thumbnail_creator.h
        types.h
        video_filters.h
        )

set(SOURCE
        random_generator.cpp
        video_filters.cpp
        )

add_library(${PROJECT_NAME} STATIC ${HEADERS} ${SOURCE})

find_package(OpenCV REQUIRED)
target_include_directories(${PROJECT_NAME} PRIVATE ${OpenCV_INCLUDE_DIRS})
target_link_directories(${PROJECT_NAME} PRIVATE ${OpenCV_DIR})

target_link_libraries(${PROJECT_NAME}
        PRIVATE ${OpenCV_LIBS}
        PRIVATE Qt5::Core
        PRIVATE stdc++fs
        PRIVATE fmt
        )
