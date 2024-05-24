cmake_minimum_required(VERSION 3.13.4)
project(libcxx)

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

add_definitions(-fvisibility-global-new-delete-hidden)
add_definitions(-fvisibility=hidden -fvisibility-inlines-hidden)
add_definitions(-DLIBCXX_BUILDING_LIBCXXABI)
add_definitions(-D_LIBCPP_NO_EXCEPTIONS)
add_definitions(-D_LIBCPP_NO_RTTI)
add_definitions(-D_LIBCPP_BUILDING_LIBRARY)
add_definitions(-D_LIBCPP_DISABLE_VISIBILITY_ANNOTATIONS)
add_definitions(-D__STDC_FORMAT_MACROS)

set(libcxx_sources
    src/algorithm.cpp
    src/any.cpp
    src/atomic.cpp
    src/barrier.cpp
    src/bind.cpp
    src/charconv.cpp
    src/chrono.cpp
    src/condition_variable.cpp
    src/condition_variable_destructor.cpp
    src/debug.cpp
    src/exception.cpp
    src/filesystem/directory_iterator.cpp
    src/filesystem/int128_builtins.cpp
    src/filesystem/operations.cpp
    src/functional.cpp
    src/future.cpp
    src/hash.cpp
    src/ios.cpp
    src/ios.instantiations.cpp
    src/iostream.cpp
    src/legacy_debug_handler.cpp
    src/legacy_pointer_safety.cpp
    src/locale.cpp
    src/memory.cpp
    src/mutex.cpp
    src/mutex_destructor.cpp
    src/new.cpp
    src/optional.cpp
    src/random_shuffle.cpp
    src/random.cpp
    src/regex.cpp
    src/shared_mutex.cpp
    src/stdexcept.cpp
    src/string.cpp
    src/strstream.cpp
    src/system_error.cpp
    src/thread.cpp
    src/typeinfo.cpp
    src/utility.cpp
    src/valarray.cpp
    src/variant.cpp
    src/vector.cpp
    src/verbose_abort.cpp
)

include_directories(include)
include_directories(include/abi)

add_library(libcxx STATIC ${libcxx_sources})

target_include_directories(libcxx PUBLIC include)
