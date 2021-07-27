# This file is part of Desktop App Toolkit,
# a set of libraries for developing nice desktop applications.
#
# For license and copyright information please follow this link:
# https://github.com/desktop-app/legal/blob/master/LEGAL

add_library(external_jthread INTERFACE IMPORTED GLOBAL)
add_library(desktop-app::external_jthread ALIAS external_jthread)

set_target_properties(external_jthread PROPERTIES LINKER_LANGUAGE CXX)

set(jthread_loc ${third_party_loc}/jthread)
set(jthread_src ${jthread_loc}/source)

nice_target_sources(external_jthread ${jthread_src}
INTERFACE
    jthread.hpp
    stop_token.hpp
)

target_include_directories(external_jthread
INTERFACE
    ${jthread_src}
)

target_link_libraries(external_jthread
INTERFACE
    external_jthread
)
