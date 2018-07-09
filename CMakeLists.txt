cmake_minimum_required (VERSION 3.11)
project(biss_analyzer)

# custom CMake Modules are located in the cmake directory.
set(CMAKE_MODULE_PATH ${PROJECT_SOURCE_DIR}/cmake)

include(ExternalAnalyzerSDK)

set(SOURCES 
src/BISSAnalyzer.cpp
src/BISSAnalyzer.h
src/BISSAnalyzerResults.cpp
src/BISSAnalyzerResults.h
src/BISSAnalyzerSettings.cpp
src/BISSAnalyzerSettings.h
src/BISSSimulationDataGenerator.cpp
src/BISSSimulationDataGenerator.h
)

add_library(biss_analyzer SHARED ${SOURCES})
target_link_libraries(biss_analyzer PRIVATE Saleae::AnalyzerSDK)

if(MSVC)
    install(TARGETS biss_analyzer RUNTIME DESTINATION "Analyzers")
else()
    install(TARGETS biss_analyzer LIBRARY DESTINATION "Analyzers")
endif()

set_post_build_destination(biss_analyzer)
