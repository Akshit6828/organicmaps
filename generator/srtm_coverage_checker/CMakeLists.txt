project(srtm_coverage_checker)

include_directories(
  ${OMIM_ROOT}/3party/jansson/src
)

set(
  SRC
  srtm_coverage_checker.cpp
)

omim_add_executable(${PROJECT_NAME} ${SRC})
target_link_libraries(${PROJECT_NAME} gflags::gflags)

omim_link_libraries(
  ${PROJECT_NAME}
  generator
  routing
  traffic
  routing_common
  indexer
  platform
  geometry
  coding
  base
  icu
  jansson
  minizip
  oauthcpp
  protobuf
  opening_hours
  succinct
  ${LIBZ}
)

link_qt5_core(${PROJECT_NAME})
