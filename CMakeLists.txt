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

add_analyzer_plugin(biss_analyzer SOURCES ${SOURCES})
