cmake_minimum_required(VERSION 3.22)


project(sx126x-drv
	VERSION 0.1
	DESCRIPTION "sx1261, sx1262, sx1268 LoRa low level driver"
	LANGUAGES C
)


set(_INC_DIR inc)
set(_SRC_DIR src)


add_library(sx126x STATIC
	inc/sx126x_api.h
	inc/sx126x_board.h
	inc/sx126x_defs.h
	inc/sx126x_drv.h

	src/sx126x_api.c
	src/sx126x_drv.c
)


target_include_directories(sx126x PUBLIC inc)

add_library(sx126x::sx126x ALIAS sx126x)
