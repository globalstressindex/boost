cmake_minimum_required(VERSION 3.5)
project(boost_config)

find_package(BCM)
include(BCMDeploy)
include(BCMSetupVersion)


bcm_setup_version(VERSION 1.64.0)

add_library(boost_config INTERFACE
)
set_property(TARGET boost_config PROPERTY EXPORT_NAME config)





bcm_deploy(TARGETS boost_config INCLUDE include NAMESPACE boost::)

add_subdirectory(test)
