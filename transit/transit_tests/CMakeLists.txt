project(transit_tests)

set(
  SRC
  transit_graph_test.cpp
  transit_json_parsing_test.cpp
  transit_schedule_tests.cpp
  transit_test.cpp
  transit_tools.hpp
)

omim_add_test(${PROJECT_NAME} ${SRC})

omim_link_libraries(
  ${PROJECT_NAME}
  indexer
  transit
  platform
  coding
  geometry
  base
  jansson
  opening_hours
  oauthcpp
  ${LIBZ}
)

link_qt5_core(${PROJECT_NAME})
