add_subdirectory(matcher)
add_subdirectory(join_order)
add_subdirectory(pushdown)
add_subdirectory(pullup)
add_subdirectory(rule)
add_subdirectory(statistics)

add_library_unity(
  duckdb_optimizer
  OBJECT
  common_aggregate_optimizer.cpp
  cse_optimizer.cpp
  deliminator.cpp
  column_lifetime_analyzer.cpp
  expression_heuristics.cpp
  filter_combiner.cpp
  filter_pushdown.cpp
  filter_pullup.cpp
  in_clause_rewriter.cpp
  optimizer.cpp
  expression_rewriter.cpp
  regex_range_filter.cpp
  remove_unused_columns.cpp
  statistics_propagator.cpp
  topn_optimizer.cpp)
set(ALL_OBJECT_FILES
    ${ALL_OBJECT_FILES} $<TARGET_OBJECTS:duckdb_optimizer>
    PARENT_SCOPE)
