# If not stated otherwise in this file or this component's license file the
# following copyright and licenses apply:
#
# Copyright 2020 RDK Management
#
# Licensed under the Apache License, Version 2.0 (the "License");
# you may not use this file except in compliance with the License.
# You may obtain a copy of the License at
#
# http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.

option(COMRPCVAULT "Include Com RPC Vault test tool" ON)

find_package(GTest REQUIRED)

set(TARGET rpc_cryptography_test)

add_executable(${TARGET} rpc_cryptography_test.cpp)

target_include_directories(${TARGET}  
    PRIVATE
        $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/..>
)

target_link_libraries(${TARGET} 
    PRIVATE
        GTest::GTest
        ${NAMESPACE}Cryptography
)

install(TARGETS ${TARGET}  
    DESTINATION bin)
