# Copyright (C) 2007-2012 LuaDist.
# Created by Peter Kapec
# Redistribution and use of this file is allowed according to the terms of the MIT license.
# For details see the COPYRIGHT file distributed with LuaDist.
# Please note that the package source code is licensed under its own license.

project ( lua_discount C )
cmake_minimum_required ( VERSION 2.8 )
include ( cmake/dist.cmake )
include ( lua )

if ( WIN32 )
  add_definitions ( -DWINDOWS )
endif ( )

install_lua_module ( discount docheader.c dumptree.c generate.c markdown.c mkdio.c resource.c 
  ldiscount.c discount.def )
install_data ( LICENSE README.mkd )
install_test ( bench.lua test_discount.lua )
