# Copyright (c) Facebook, Inc. and its affiliates.
#
# This source code is licensed under the MIT license found in the LICENSE
# file in the root directory of this source tree.

set(LLVM_LINK_COMPONENTS
  Analysis
  Core
  Support
  )

set(BCSources
  BytecodeFileFormatTest.cpp
  BytecodeFormConverterTest.cpp
  RATest.cpp
  SupportTest.cpp
  TestHelpers.cpp
  HBC.cpp
  DebugInfo.cpp
  )

add_hermes_unittest(HermesBCGenTests
  ${BCSources}
  )

target_link_libraries(HermesBCGenTests
 hermesHBCBackend
 hermesBackend
 hermesFrontend
 hermesSupport
 hermesOptimizer
 hermesVMRuntime
 dtoa
 )
