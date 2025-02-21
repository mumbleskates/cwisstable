# Copyright 2022 Google LLC
#
# Licensed under the Apache License, Version 2.0 (the "License");
# you may not use this file except in compliance with the License.
# You may obtain a copy of the License at
#
#      http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.

cc_library(
    name = "wrappers",
    hdrs = ["wrappers.h"],
    deps = ["//:unified"],
    copts = [
      "-std=c++17",
    ],
)

cc_test(
    name = "raw_hash_set_test",
    srcs = ["absl_raw_hash_set_test.cc"],
    deps = [
        "//:unified",
        "//:debug",
        ":wrappers",

        "@com_google_absl//absl/base",
        "@com_google_absl//absl/base:config",
        "@com_google_absl//absl/base:core_headers",
        "@com_google_absl//absl/strings",
        "@com_google_googletest//:gtest_main",
    ],
    copts = [
      "-std=c++17",
      #"-DSWISS_HAVE_SSE2=0",
    ],
)

cc_binary(
    name = "raw_hash_set_benchmark",
    testonly = 1,
    srcs = ["absl_raw_hash_set_benchmark.cc"],
    tags = ["benchmark"],
    visibility = ["//visibility:private"],
    deps = [
        "//:unified",
        "//:debug",
        ":wrappers",
        
        "@com_google_absl//absl/strings:str_format",
        "@com_github_google_benchmark//:benchmark_main",
    ],
    copts = [
      "-std=c++17",
      #"-DSWISS_HAVE_SSE2=0",
    ],
)
