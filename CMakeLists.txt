cmake_minimum_required(VERSION 3.0)

project(chess_network)

set(CMAKE_CXX_STANDARD 14)

set(CMAKE_AUTOMOC ON)
set(CMAKE_AUTOUIC ON)
set(CMAKE_AUTORCC ON)

set(CMAKE_PREFIX_PATH "/Volumes/Extend/Qt/5.12.0/clang_64")

set(Qt5_DIR "${CMAKE_PREFIX_PATH}/lib/cmake/Qt5")
set(Qt5Widgets_DIR "${CMAKE_PREFIX_PATH}/lib/cmake/Qt5Widgets")
set(Qt5Network_DIR "${CMAKE_PREFIX_PATH}/lib/cmake/Qt5Network")
set(Qt5LinguistTools_DIR "${CMAKE_PREFIX_PATH}/lib/cmake/Qt5LinguistTools")

find_package(Qt5 REQUIRED Widgets)
find_package(Qt5 REQUIRED Core)
find_package(Qt5 REQUIRED Opengl)
find_package(Qt5 REQUIRED Gui)
find_package(Qt5 REQUIRED NetWork)

add_executable(chess_network
        board.h board.cpp
        ctrlpanel.h ctrlpanel.cpp
        main.cpp
        mainwnd.h mainwnd.cpp
        step.h step.cpp
        stone.h stone.cpp
        widget.h widget.cpp
        singlegame.h singlegame.cpp
        choosedlg.h choosedlg.cpp
        netgame.h netgame.cpp
        )

target_link_libraries(chess_network Qt5::Widgets Qt5::Network
        Qt5::Gui
        )