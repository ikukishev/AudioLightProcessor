
add_executable(artnet_test WIN32 MACOSX_BUNDLE
    artnet_test.cpp artnet_test.h
)
target_include_directories(artnet_test PRIVATE
    ../src
)

find_package(Qt6 REQUIRED COMPONENTS Test)

target_link_libraries(artnet_test PRIVATE
    Qt6::Core
    Qt6::Network
    Qt::Test
    artnet
)

# Consider using qt_generate_deploy_app_script() for app deployment if
# the project can use Qt 6.3. In that case rerun qmake2cmake with
# --min-qt-version=6.3.
