# Copyright (C) 2007-2009 LuaDist.
# Created by Peter Kapec
# Redistribution and use of this file is allowed according to the terms of the MIT license.
# For details see the COPYRIGHT file distributed with LuaDist.
# Please note that the package source code is licensed under its own license.

PROJECT(lua_discount C)
CMAKE_MINIMUM_REQUIRED(VERSION 2.8)
INCLUDE(dist.cmake)

# Build
INCLUDE_DIRECTORIES(.)

IF(WIN32)
	ADD_DEFINITIONS(-DWINDOWS)
ENDIF()

ADD_LUA_MODULE(discount docheader.c dumptree.c generate.c markdown.c mkdio.c resource.c ldiscount.c discount.def)

# Install all files and documentation
INSTALL (TARGETS discount DESTINATION ${INSTALL_CMOD})
INSTALL (FILES LICENSE README.mkd DESTINATION ${INSTALL_DATA})
INSTALL (FILES bench.lua test_discount.lua DESTINATION ${INSTALL_TEST})
