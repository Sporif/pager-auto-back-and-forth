
cmake_minimum_required(VERSION 3.27)

project(pager-auto-back-and-forth)

set(CMAKE_CXX_STANDARD 23)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

set(QT_MIN_VERSION "6.4.0")
set(KF6_MIN_VERSION "6.0.0")

find_package(ECM ${KF6_MIN_VERSION} REQUIRED NO_MODULE)
set(CMAKE_MODULE_PATH ${ECM_MODULE_PATH})

include(KDEInstallDirs)
include(KDECMakeSettings)
include(KDECompilerSettings NO_POLICY_SCOPE)
# include(ECMQtDeclareLoggingCategory)

set(CMAKE_AUTOMOC ON)
set(CMAKE_AUTORCC ON)
set(CMAKE_AUTOUIC ON)

find_package(Qt6 ${QT_MIN_VERSION} REQUIRED COMPONENTS Core DBus Qml)
find_package(KF6 ${KF6_MIN_VERSION} REQUIRED COMPONENTS Service WindowSystem)
find_package(Plasma ${KF6_MIN_VERSION} REQUIRED)
find_package(PlasmaActivities ${KF6_MIN_VERSION} REQUIRED)

add_subdirectory(plugin)
plasma_install_package(package com.sporif.pager)

install()
