set(COMPONENT_NAME projectconfig)

set(SRC
    projectconfig.ui
    projectconfig.cpp    
    canrawviewmodel.cpp
    canrawsendermodel.cpp
    candevicemodel.cpp
    canrawplayermodel.cpp
    canrawloggermodel.cpp
    canloadmodel.cpp
    canrawfiltermodel.cpp
    dragwidget.cpp
    flowviewwrapper.cpp
    projectconfigvalidator.cpp
    propertyeditordialog.cpp
    propertyeditordialog.ui
	../../../CANdevResources.qrc
)

add_definitions(-DRAPIDJSON_HAS_STDSTRING=1 -DRAPIDJSON_HAS_CXX11_RVALUE_REFS=1)

add_library(${COMPONENT_NAME} STATIC ${SRC})
include_directories("${CMAKE_CURRENT_SOURCE_DIR}/..")
include_directories("${CMAKE_CURRENT_SOURCE_DIR}/../../../3rdParty/rapidjson/include")
target_link_libraries(${COMPONENT_NAME} Qt5::Widgets Qt5::Core Qt5::SerialBus nodes candevice canrawview canrawsender cds-common canrawplayer canrawlogger canload canrawfilter)
target_include_directories(${COMPONENT_NAME} INTERFACE ${CMAKE_CURRENT_SOURCE_DIR})


