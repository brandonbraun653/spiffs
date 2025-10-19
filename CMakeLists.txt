include(CTEmbedded)

gen_intf_lib(
  TARGET
    spiffs_intf_inc
  INTF_INCLUDES
    ./src
    ./src/default
  INTF_LIBRARIES
    segger_sys_view_intf
  EXPORT_DIR
    "${PROJECT_BINARY_DIR}/Aurora/SPIFFS"
)

gen_static_lib_variants(
  TARGET
    aurora_filesystem_spiffs_core
  SOURCES
    src/spiffs_cache.c
    src/spiffs_check.c
    src/spiffs_gc.c
    src/spiffs_hydrogen.c
    src/spiffs_nucleus.c
  PRV_LIBRARIES
    spiffs_intf_inc
  EXPORT_DIR
    "${PROJECT_BINARY_DIR}/Aurora/SPIFFS"
)
