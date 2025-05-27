# Copyright (c) 2006, 2010, Oracle and/or its affiliates. All rights reserved.
# 
# This program is free software; you can redistribute it and/or modify
# it under the terms of the GNU General Public License as published by
# the Free Software Foundation; version 2 of the License.
# 
# This program is distributed in the hope that it will be useful,
# but WITHOUT ANY WARRANTY; without even the implied warranty of
# MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
# GNU General Public License for more details.
# 
# You should have received a copy of the GNU General Public License
# along with this program; if not, write to the Free Software
# Foundation, Inc., 51 Franklin St, Fifth Floor, Boston, MA  02110-1335 USA

INCLUDE_DIRECTORIES(${CMAKE_SOURCE_DIR})

MYSQL_ADD_PLUGIN(ftexample example/plugin_example.c
  MODULE_ONLY MODULE_OUTPUT_NAME "mypluglib" COMPONENT Test)

# Ngram parser
MYSQL_ADD_PLUGIN(ngram_parser
  ngram_parser/plugin_ngram.cc
  MODULE_OUTPUT_NAME "ngram"
  MODULE_ONLY
  )

IF(WITH_DEBUG)
  ADD_DEFINITIONS(-DDEBUG)
ENDIF()

