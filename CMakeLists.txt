# MCCI Arduino LoRaWAN Library.
# https://github.com/mcci-catena/arduino-lorawan
# MIT License

cmake_minimum_required(VERSION 3.5)

set(TTN_SRCS
    src/lib/ttn_base_netjoin.cpp
    src/lib/ttn_as923_netjoin.cpp
    src/lib/ttn_au915_netjoin.cpp
    src/lib/ttn_eu868_netjoin.cpp
    src/lib/ttn_in866_netjoin.cpp
    src/lib/ttn_kr920_netjoin.cpp
    src/lib/ttn_us915_netjoin.cpp
    src/lib/ttn_as923_netbeginregioninit.cpp
    src/lib/ttn_au915_netbeginregioninit.cpp
    src/lib/ttn_eu868_netbeginregioninit.cpp
    src/lib/ttn_in866_netbeginregioninit.cpp
    src/lib/ttn_kr920_netbeginregioninit.cpp
    src/lib/ttn_us915_netbeginregioninit.cpp
)

set(ACTILITY_SRCS
    src/lib/actility_base_netjoin.cpp
    src/lib/actility_as923_netjoin.cpp
    src/lib/actility_au915_netjoin.cpp
    src/lib/actility_eu868_netjoin.cpp
    src/lib/actility_in866_netjoin.cpp
    src/lib/actility_kr920_netjoin.cpp
    src/lib/actility_us915_netjoin.cpp
    src/lib/actility_as923_netbeginregioninit.cpp
    src/lib/actility_au915_netbeginregioninit.cpp
    src/lib/actility_eu868_netbeginregioninit.cpp
    src/lib/actility_in866_netbeginregioninit.cpp
    src/lib/actility_kr920_netbeginregioninit.cpp
    src/lib/actility_us915_netbeginregioninit.cpp
)

set(HELIUM_SRCS
    src/lib/helium_base_netjoin.cpp
    src/lib/helium_us915_netjoin.cpp
    src/lib/helium_us915_netbeginregioninit.cpp
)

set(MACHINEQ_SRCS
    src/lib/machineq_base_netjoin.cpp
    src/lib/machineq_us915_netjoin.cpp
    src/lib/machineq_us915_netbeginregioninit.cpp
)

set(SENET_SRCS
    src/lib/senet_base_netjoin.cpp
    src/lib/senet_us915_netjoin.cpp
    src/lib/senet_us915_netbeginregioninit.cpp
)

set(SENRA_SRCS
    src/lib/senra_base_netjoin.cpp
    src/lib/senra_in866_netjoin.cpp
    src/lib/senra_in866_netbeginregioninit.cpp
)

set(SWISSCOM_SRCS
    src/lib/swisscom_base_netjoin.cpp
    src/lib/swisscom_eu868_netjoin.cpp
    src/lib/swisscom_eu868_netbeginregioninit.cpp
)

set(CHIRPSTACK_SRCS
    src/lib/chirpstack_base_netjoin.cpp
    src/lib/chirpstack_as923_netjoin.cpp
    src/lib/chirpstack_au915_netjoin.cpp
    src/lib/chirpstack_eu868_netjoin.cpp
    src/lib/chirpstack_in866_netjoin.cpp
    src/lib/chirpstack_kr920_netjoin.cpp
    src/lib/chirpstack_us915_netjoin.cpp
    src/lib/chirpstack_as923_netbeginregioninit.cpp
    src/lib/chirpstack_au915_netbeginregioninit.cpp
    src/lib/chirpstack_eu868_netbeginregioninit.cpp
    src/lib/chirpstack_in866_netbeginregioninit.cpp
    src/lib/chirpstack_kr920_netbeginregioninit.cpp
    src/lib/chirpstack_us915_netbeginregioninit.cpp
)

set(GENERIC_SRCS
    src/lib/generic_base_netjoin.cpp
    src/lib/generic_as923_netjoin.cpp
    src/lib/generic_au915_netjoin.cpp
    src/lib/generic_eu868_netjoin.cpp
    src/lib/generic_in866_netjoin.cpp
    src/lib/generic_kr920_netjoin.cpp
    src/lib/generic_us915_netjoin.cpp
    src/lib/generic_as923_netbeginregioninit.cpp
    src/lib/generic_au915_netbeginregioninit.cpp
    src/lib/generic_eu868_netbeginregioninit.cpp
    src/lib/generic_in866_netbeginregioninit.cpp
    src/lib/generic_kr920_netbeginregioninit.cpp
    src/lib/generic_us915_netbeginregioninit.cpp
)

set(LORAWAN_SRCS
    src/lib/arduino_lorawan.cpp
    src/lib/arduino_lorawan_begin.cpp
    src/lib/arduino_lorawan_cEventLog.cpp
    src/lib/arduino_lorawan_loop.cpp
    src/lib/arduino_lorawan_sessionstate.cpp
    src/lib/arduino_lorawan_shutdown.cpp
)

set(OTHER_SRCS
    src/lib/LogPrintf.cpp
    src/lib/GetCountryCode.cpp
    src/lib/GetRegion.cpp
    src/lib/GetRegionString.cpp
    src/lib/GetTxReady.cpp
    src/lib/SendBuffer.cpp
    src/lib/SetLinkCheckMode.cpp
)

set(srcs
    ${TTN_SRCS}
    ${ACTILITY_SRCS}
    ${HELIUM_SRCS}
    ${MACHINEQ_SRCS}
    ${SENET_SRCS}
    ${SENRA_SRCS}
    ${SWISSCOM_SRCS}
    ${CHIRPSTACK_SRCS}
    ${GENERIC_SRCS}
    ${LORAWAN_SRCS}
    ${OTHER_SRCS}
)

idf_component_register(
    SRCS ${srcs}
    INCLUDE_DIRS src
    REQUIRES Catena-mcciadk arduino-lmic)

target_compile_options(${COMPONENT_TARGET} PUBLIC
    -DARDUINO_TTGO_LoRa32_V1)

project(arduino-lorawan)
