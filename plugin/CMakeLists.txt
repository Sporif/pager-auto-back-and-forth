qt_policy(SET QTP0001 NEW)

set(pager_source
        pagermodel.cpp
        pagermodel.h
        windowmodel.cpp
        windowmodel.h
)

find_package(LibTaskManager REQUIRED)

qt_add_qml_module(pager
    URI "com.sporif.pager"
    VERSION 1.0
    SOURCES ${pager_source}
)

# ecm_qt_declare_logging_category(com.sporif.pager
#     HEADER log_settings.h
#     IDENTIFIER PAGER_DEBUG
#     CATEGORY_NAME com.sporif.pager
# )

set_target_properties(pagerplugin PROPERTIES
    PREFIX "lib"
)

target_include_directories(pager PRIVATE
    ${CMAKE_CURRENT_SOURCE_DIR}
)

target_link_libraries(pager
    PRIVATE
        KF6::WindowSystem
        Plasma::Plasma
        Plasma::Activities
        PW::LibTaskManager
        Qt::Core
        Qt::DBus
        Qt::Qml
        Qt::Quick
)

install(TARGETS pager
    DESTINATION ${KDE_INSTALL_LIBDIR}
)

install(TARGETS pagerplugin
    DESTINATION ${KDE_INSTALL_QMLDIR}/com/sporif/pager
)

install(FILES
    ${CMAKE_CURRENT_BINARY_DIR}/qmldir
    ${CMAKE_CURRENT_BINARY_DIR}/pager.qmltypes
    DESTINATION ${KDE_INSTALL_QMLDIR}/com/sporif/pager
)
