FILE(GLOB INSTALLER_FILES *.py)
SET(INSTALLER_FILES ${INSTALLER_FILES})

FILE(GLOB UI_FILES *.ui)
PYQT4_WRAP_UI(PYUI_FILES ${UI_FILES})
PYQT4_ADD_RESOURCES(PYRC_FILES resources.qrc)
#ADD_CUSTOM_TARGET(gdaltools ALL DEPENDS ${PYUI_FILES} ${PYRC_FILES})

SET(INSTALLER_FILES ${INSTALLER_FILES} ${PYUI_FILES} ${PYRC_FILES})

#INSTALL(FILES ${INSTALLER_FILES} DESTINATION ${QGIS_DATA_DIR}/python/plugins/GdalTools)
PLUGIN_INSTALL(GdalTools . ${INSTALLER_FILES} __init__.py)

ADD_SUBDIRECTORY(tools)
ADD_SUBDIRECTORY(icons)
