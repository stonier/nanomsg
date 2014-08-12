##############################################################################
# Cmake
##############################################################################

cmake_minimum_required(VERSION 2.8.3)
project(nanomsg)

##############################################################################
# Find Packages
##############################################################################

find_package(catkin REQUIRED)

##############################################################################
# Catkin
##############################################################################

catkin_package(
  INCLUDE_DIRS .
  LIBRARIES ${PROJECT_NAME}
  # DEPENDS # should somehow get -pthreads and -lanl in here
)

##############################################################################
# Project Configuration
##############################################################################

# These have been blindly grabbed from a ./configure on ubuntu amd64 trusty
set(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -std=gnu99")
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=gnu99")
add_definitions(
    -DHAVE_PTHREAD_PRIO_INHERIT
    -DSTDC_HEADERS
    -DHAVE_SYS_TYPES_H
    -DHAVE_SYS_STAT_H
    -DHAVE_STDLIB_H
    -DHAVE_STRING_H
    -DHAVE_MEMORY_H
    -DHAVE_STRINGS_H
    -DHAVE_INTTYPES_H
    -DHAVE_STDINT_H
    -DHAVE_UNISTD_H
    -DHAVE_NETINET_IN_H
    -DHAVE_NETDB_H
    -DHAVE_ARPA_INET_H
    -DHAVE_UNISTD_H
    -DHAVE_SYS_SOCKET_H
    -DHAVE_SYS_IOCTL_H
    -DNN_HAVE_STDINT
    -DHAVE_EVENTFD
    -DNN_HAVE_EVENTFD
    -DHAVE_PIPE
    -DNN_HAVE_PIPE
    -DHAVE_PIPE2
    -DNN_HAVE_PIPE2
    -DHAVE_CLOCK_GETTIME
    -DHAVE_POLL
    -DNN_HAVE_POLL
    -DHAVE_EPOLL_CREATE
    -DNN_USE_EPOLL
    -DHAVE_GETIFADDRS
    -DNN_USE_IFADDRS
    -DHAVE_ACCEPT4
    -DNN_HAVE_ACCEPT4
    -DNN_HAVE_GETADDRINFO_A
    -DNN_HAVE_SOCKETPAIR
    -DNN_HAVE_SEMAPHORE
    -DNN_HAVE_GCC_ATOMIC_BUILTINS
    -DNN_USE_EVENTFD
    -DHAVE_DLFCN_H
    -D_GNU_SOURCE -D_GNU_SOURCE -D_GNU_SOURCE
)

##############################################################################
# Sources
##############################################################################

add_subdirectory(nanomsg)
