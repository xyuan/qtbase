# Generated from embeddedintoforeignwindow.pro.

#####################################################################
## embeddedintoforeignwindow Binary:
#####################################################################

add_qt_manual_test(embeddedintoforeignwindow
    SOURCES
        ../diaglib/eventfilter.cpp ../diaglib/eventfilter.h
        ../diaglib/nativewindowdump.h
        ../diaglib/qwindowdump.cpp ../diaglib/qwindowdump.h
        ../diaglib/textdump.cpp ../diaglib/textdump.h
        itemwindow.cpp itemwindow.h
        main.cpp
    DEFINES
        QT_DIAG_LIB
    INCLUDE_DIRECTORIES
        ../diaglib
    PUBLIC_LIBRARIES
        Qt::CorePrivate
        Qt::Gui
        Qt::GuiPrivate
)

#### Keys ignored in scope 1:.:.:embeddedintoforeignwindow.pro:<TRUE>:
# TEMPLATE = "app"

## Scopes:
#####################################################################

extend_target(embeddedintoforeignwindow CONDITION WIN32 AND NOT WINRT
    SOURCES
        ../diaglib/nativewindowdump_win.cpp
    PUBLIC_LIBRARIES
        user32
)

extend_target(embeddedintoforeignwindow CONDITION UNIX OR WINRT
    SOURCES
        ../diaglib/nativewindowdump.cpp
)

extend_target(embeddedintoforeignwindow CONDITION QT_FEATURE_widgets
    SOURCES
        ../diaglib/debugproxystyle.cpp ../diaglib/debugproxystyle.h
        ../diaglib/logwidget.cpp ../diaglib/logwidget.h
        ../diaglib/qwidgetdump.cpp ../diaglib/qwidgetdump.h
    PUBLIC_LIBRARIES
        Qt::WidgetsPrivate
)

extend_target(embeddedintoforeignwindow CONDITION QT_FEATURE_opengl
    SOURCES
        ../diaglib/glinfo.cpp ../diaglib/glinfo.h
    PUBLIC_LIBRARIES
        Qt::OpenGL
)
