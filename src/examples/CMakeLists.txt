#add_subdirectory(aes128)
#add_subdirectory(benchmark_integers)
#add_subdirectory(benchmark_primitive_operations)
#add_subdirectory(benchmark_providers)
#add_subdirectory(example_template)
#add_subdirectory(sha256)
#add_subdirectory(tutorial/crosstabs)
#add_subdirectory(tutorial/innerproduct)
#add_subdirectory(tutorial/mult3)
#add_subdirectory(millionaires_problem)

add_executable(astra_benchmark astra_benchmark.cpp DEtI_benchmarks.cpp)
add_executable(auxiliator_benchmark auxiliator_benchmark.cpp DEtI_benchmarks.cpp)
add_executable(socium_benchmark socium_benchmark.cpp DEtI_benchmarks.cpp)
add_executable(swift_benchmark swift_benchmark.cpp DEtI_benchmarks.cpp)

if (NOT MOTION_BUILD_BOOST_FROM_SOURCES)
    find_package(Boost
            COMPONENTS
            program_options
            REQUIRED)
endif ()

target_link_libraries(astra_benchmark
        MOTION::motion
        Boost::program_options
        )

target_link_libraries(auxiliator_benchmark
        MOTION::motion
        Boost::program_options
        )

target_link_libraries(socium_benchmark
        MOTION::motion
        Boost::program_options
        )

target_link_libraries(swift_benchmark
        MOTION::motion
        Boost::program_options
        )
