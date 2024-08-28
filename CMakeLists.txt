#
# Copyright (c) 2022 Nordic Semiconductor ASA
#
# SPDX-License-Identifier: LicenseRef-Nordic-5-Clause
#

# Turn off precondition checking and logging to reduce the code footprint and RAM usage
target_compile_definitions(app PRIVATE
	AZ_NO_PRECONDITION_CHECKING
	AZ_NO_LOGGING
)

target_include_directories(app PRIVATE
	${CMAKE_CURRENT_SOURCE_DIR}/sdk/inc
)

target_sources(app PRIVATE
	# Azure SDK for C - CORE lib
	${CMAKE_CURRENT_SOURCE_DIR}/sdk/src/azure/core/az_context.c
	${CMAKE_CURRENT_SOURCE_DIR}/sdk/src/azure/core/az_json_reader.c
	${CMAKE_CURRENT_SOURCE_DIR}/sdk/src/azure/core/az_json_token.c
	${CMAKE_CURRENT_SOURCE_DIR}/sdk/src/azure/core/az_json_writer.c
	${CMAKE_CURRENT_SOURCE_DIR}/sdk/src/azure/core/az_span.c

	# Azure SDK for C - IoT lib
	${CMAKE_CURRENT_SOURCE_DIR}/sdk/src/azure/iot/az_iot_common.c
	${CMAKE_CURRENT_SOURCE_DIR}/sdk/src/azure/iot/az_iot_hub_client.c
	${CMAKE_CURRENT_SOURCE_DIR}/sdk/src/azure/iot/az_iot_hub_client_c2d.c
	${CMAKE_CURRENT_SOURCE_DIR}/sdk/src/azure/iot/az_iot_hub_client_commands.c
	${CMAKE_CURRENT_SOURCE_DIR}/sdk/src/azure/iot/az_iot_hub_client_methods.c
	${CMAKE_CURRENT_SOURCE_DIR}/sdk/src/azure/iot/az_iot_hub_client_properties.c
	${CMAKE_CURRENT_SOURCE_DIR}/sdk/src/azure/iot/az_iot_hub_client_telemetry.c
	${CMAKE_CURRENT_SOURCE_DIR}/sdk/src/azure/iot/az_iot_hub_client_twin.c
	${CMAKE_CURRENT_SOURCE_DIR}/sdk/src/azure/iot/az_iot_provisioning_client.c
)
