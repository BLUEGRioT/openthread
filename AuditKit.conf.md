Ligne de commande pour la compilation de la library openthread pour auditKit : 

Compilation router :

	make -f examples/Makefile-nrf52840 DISABLE_BUILTIN_MBEDTLS=1 DNS_CLIENT=1 JOINER=1 MAC_FILTER=1 SERVICE=1 UDP_FORWARD=1 ECDSA=1 SNTP_CLIENT=1 COAPS=1 DHCP6_SERVER=1 DHCP6_CLIENT=1 DISABLE_TRANSPORTS=1

Compilation Border router :

	make -f examples/Makefile-nrf52840 BORDER_AGENT=1 BORDER_ROUTER=1 COAP=1 COMMISSIONER=1 DISABLE_BUILTIN_MBEDTLS=1 DNS_CLIENT=1 DIAGNOSTIC=1 EXTERNAL_HEAP=1 JOINER=1 LINK_RAW=1 MAC_FILTER=1 MTD_NETDIAG=1 SERVICE=1 UDP_FORWARD=1 ECDSA=1 SNTP_CLIENT=1 COAPS=1 DHCP6_SERVER=1 DHCP6_CLIENT=1 NCP_SPI=1

	arm-none-eabi-objcopy -O ihex output/nrf52840/bin/ot-rcp output/nrf52840/bin/ot-rcp.hex

Option FULL_LOGS=1 pour avoir les Logs


Une fois compilé, il faut les library suivantes :

	- openthread/build/nrf52840/examples/platforms/nrf528xx/libopenthread-nrf52840-sdk.a
	- openthread/build/nrf52840/examples/platforms/nrf528xx/libopenthread-nrf52840-transport.a
	- openthread/build/nrf52840/examples/platforms/utils/libopenthread-platform-utils.a
	- openthread/build/nrf52840/src/core/libopenthread-ftd.a
	- openthread/build/nrf52840/third_party/NordicSemiconductor/libnordicsemi-nrf52840-radio-driver.a

