# Licensed to the Apache Software Foundation (ASF) under one
# or more contributor license agreements.  See the NOTICE file
# distributed with this work for additional information
# regarding copyright ownership.  The ASF licenses this file
# to you under the Apache License, Version 2.0 (the
# "License"); you may not use this file except in compliance
# with the License.  You may obtain a copy of the License at
#
#   http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing,
# software distributed under the License is distributed on an
# "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY
# KIND, either express or implied.  See the License for the
# specific language governing permissions and limitations
# under the License.

add_library(common_test OBJECT "")

set_target_properties(common_test PROPERTIES
  CXX_STANDARD 11
  CXX_STANDARD_REQUIRED YES
)

target_include_directories(common_test
  INTERFACE
    ${CMAKE_CURRENT_SOURCE_DIR}
)

target_sources(common_test
  INTERFACE
    ${CMAKE_CURRENT_SOURCE_DIR}/catch.hpp  
    ${CMAKE_CURRENT_SOURCE_DIR}/test_allocator.hpp
    ${CMAKE_CURRENT_SOURCE_DIR}/test_type.hpp
  PRIVATE
    ${CMAKE_CURRENT_SOURCE_DIR}/catch_runner.cpp
    ${CMAKE_CURRENT_SOURCE_DIR}/test_allocator.cpp
)
