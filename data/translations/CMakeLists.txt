set(TRANSLATION_FILES
    cs.ts
    fi.ts
    it.ts
    ro.ts
    ru.ts
    tr.ts
    pt_BR.ts
    zh_CN.ts
)

if(USE_QT5)
    qt5_add_translation(QM_FILES ${TRANSLATION_FILES})
else()
    qt4_add_translation(QM_FILES ${TRANSLATION_FILES})
endif()

install(FILES ${QM_FILES} DESTINATION ${COMPONENTS_TRANSLATION_DIR})

add_custom_target(components-translation DEPENDS ${QM_FILES})
