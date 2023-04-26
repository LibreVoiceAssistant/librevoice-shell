PROJECT(libre-shell)

SET(libre-shell_SRC
    main.cpp
    appsettings.cpp
    speechintent.cpp
    plugins/EnvironmentSummary.cpp
    plugins/ResetOperations.cpp
)

set(libre-shell_EXTRA_LIBS
        Qt5::Widgets
        KF5::DBusAddons
        KF5::Kirigami2
    )

qt5_add_resources(ovos-shell_SRC
    qml.qrc
)

add_executable(libre-shell ${libre-shell_SRC})
target_link_libraries(libre-shell Qt5::Core Qt5::Quick Qt5::WebView ${libre-shell_EXTRA_LIBS})

install(TARGETS libre-shell ${INSTALL_TARGETS_DEFAULT_ARGS})
install( PROGRAMS libre-shell.desktop DESTINATION  ${KDE_INSTALL_APPDIR} )
