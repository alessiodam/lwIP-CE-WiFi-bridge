set(proto_dir "${CMAKE_CURRENT_LIST_DIR}/../../src/wireless")
if(NOT EXISTS "${proto_dir}/wifi_proto.h")
    set(proto_dir "${CMAKE_CURRENT_LIST_DIR}/../../lwip-ce/src/wireless")
endif()

idf_component_register(SRCS "main.c" "bridge.c" "control.c" "crypto.c" "wifi.c" "profiles.c" "console.c"
                       INCLUDE_DIRS "."
                       PRIV_INCLUDE_DIRS "${proto_dir}"
                       REQUIRES usb usb_host_cdc_acm esp_event esp_wifi nvs_flash esp_driver_gpio esp_driver_uart mbedtls esp_app_format wpa_supplicant)
