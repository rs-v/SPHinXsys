add_library(structural_simulation_module structural_simulation_class.cpp structural_simulation_class.h)
target_include_directories(structural_simulation_module PUBLIC $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}>)
target_include_directories(structural_simulation_module PUBLIC $<INSTALL_INTERFACE:include/structural_simulation>)
target_link_libraries(structural_simulation_module PUBLIC sphinxsys_3d)

install(TARGETS structural_simulation_module
    EXPORT SPHinXsysTargets
    ARCHIVE DESTINATION ${CMAKE_INSTALL_LIBDIR}
    LIBRARY DESTINATION ${CMAKE_INSTALL_LIBDIR}
    RUNTIME DESTINATION ${CMAKE_INSTALL_BINDIR})
install(FILES structural_simulation_class.h
    DESTINATION ${CMAKE_INSTALL_INCLUDEDIR}/structural_simulation)
