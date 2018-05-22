# Copyright 2016 The Bazel Authors. All rights reserved.
#
# Licensed under the Apache License, Version 2.0 (the "License");
# you may not use this file except in compliance with the License.
# You may obtain a copy of the License at
#
#    http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.

package(default_visibility = ["//visibility:public"])

java_runtime_suite(
    name = "jdk8",
    default = ":jdk8-default",
)

java_runtime(
    name = "jdk8-default",
    srcs = [],
    java_home = "/usr/lib/jvm/java-8-openjdk-amd64",
)

# Latest RBE Ubuntu16_04 container
# Update every time when a new container is released.
alias(
    name = "rbe_ubuntu1604",
    actual = ":rbe_ubuntu1604_r328903",
)

# RBE Ubuntu16_04 r328903
platform(
    name = "rbe_ubuntu1604_r328903",
    constraint_values = [
        "@bazel_tools//platforms:x86_64",
        "@bazel_tools//platforms:linux",
        "@bazel_tools//tools/cpp:clang",
        "//constraints:xenial",
        "//constraints/sanitizers:support_msan",
    ],
    remote_execution_properties = """
          properties: {
            name: "container-image"
            value:"docker://gcr.io/cloud-marketplace/google/rbe-ubuntu16-04@sha256:b940d4f08ea79ce9a07220754052da2ac4a4316e035d8799769cea3c24d10c66"
         }
         """,
)