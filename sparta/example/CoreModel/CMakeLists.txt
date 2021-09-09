project(CORE_MODEL_PIPELINE)

include (../ExamplesMacros.cmake)
add_compile_options(-std=c++17)
set(sparta_home $ENV{SPARTA_HOME})
add_executable(sparta_core_example
  src/main.cpp
  src/Core.cpp
  src/ExampleSimulation.cpp
  src/Fetch.cpp
  src/Decode.cpp
  src/Rename.cpp
  src/Dispatch.cpp
  src/Execute.cpp
  src/ExampleInst.cpp
  src/ROB.cpp
  src/LSU.cpp
  src/BIU.cpp
  src/MSS.cpp
  src/Preloader.cpp
  src/CPU.cpp
  src/CPUFactory.cpp
  src/CPUTopology.cpp
  )

target_include_directories(sparta_core_example PUBLIC ${sparta_home}/include /imec/users/bhatta53/memseat/ekanta/map/sparta)
target_link_directories(sparta_core_example PUBLIC $ENV{SPARTA_INSTALL_HOME}/lib)


target_link_libraries(sparta_core_example 
        pthread
            sparta simdb 
                yaml-cpp sqlite3 boost_serialization boost_filesystem boost_timer hdf5 z boost_program_options 
                    )

                #sparta_application(sparta_core_example)

