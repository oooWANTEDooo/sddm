configure_file(${CMAKE_SOURCE_DIR}/data/sddm.conf.in    ${CMAKE_BINARY_DIR}/sddm.conf)

install(DIRECTORY   faces                               DESTINATION ${DATA_INSTALL_DIR})
install(DIRECTORY   flags                               DESTINATION ${DATA_INSTALL_DIR})

install(FILES       "${CMAKE_BINARY_DIR}/sddm.conf"     DESTINATION ${SYS_CONFIG_DIR})
install(FILES       "${CMAKE_BINARY_DIR}/sddm.conf"     DESTINATION ${DATA_INSTALL_DIR} RENAME sddm.conf.sample)

install(FILES org.freedesktop.DisplayManager.conf       DESTINATION ${DBUS_CONFIG_DIR})

install(FILES scripts/Xsession DESTINATION ${DATA_INSTALL_DIR}/scripts
        PERMISSIONS OWNER_READ OWNER_WRITE OWNER_EXECUTE
        GROUP_READ GROUP_EXECUTE
        WORLD_READ WORLD_EXECUTE)

add_subdirectory(themes)
add_subdirectory(translations)
