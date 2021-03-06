# This file is part of the CMaNGOS Project. See AUTHORS file for Copyright information
#
# This file is free software; as a special exception the author gives
# unlimited permission to copy and/or distribute it, with or without
# modifications, as long as this notice is preserved.
#
# This program is distributed in the hope that it will be useful, but
# WITHOUT ANY WARRANTY, to the extent permitted by law; without even the
# implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.

cmake_minimum_required (VERSION 2.6)
project (MANGOS_VMAP_EXTRACT_IO)

# uncomment next line to disable debug mode
ADD_DEFINITIONS("-DIOMAP_DEBUG")
# build setup currently only supports libmpq 0.4.x
ADD_DEFINITIONS("-DUSE_LIBMPQ04")
ADD_DEFINITIONS("-Wall")
ADD_DEFINITIONS("-ggdb")
ADD_DEFINITIONS("-O3")

if (APPLE)
  add_definitions("-Dfopen64=fopen")
  add_definitions("-Dfseeko64=fseeko")
  add_definitions("-Dfseek64=fseek")
  add_definitions("-Dftell64=ftell")
  add_definitions("-Dftello64=ftello")
endif()

include_directories(../../dep/libmpq)

add_subdirectory(vmapextract)
