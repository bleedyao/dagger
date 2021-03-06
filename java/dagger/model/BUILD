# Copyright (C) 2017 The Dagger Authors.
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

# Description:
#   Dagger's core APIs exposed for plugins

package(default_visibility = ["//:src"])

load(
    "//:build_defs.bzl",
    "DOCLINT_HTML_AND_SYNTAX",
    "DOCLINT_REFERENCES",
)

filegroup(
    name = "model-srcs",
    srcs = glob(["*.java"]),
)

java_library(
    name = "model",
    srcs = [":model-srcs"],
    javacopts = DOCLINT_HTML_AND_SYNTAX + DOCLINT_REFERENCES,
    deps = [
        "//java/dagger:core",
        "//third_party:auto_common",
        "//third_party:auto_value",
        "//third_party:error_prone_annotations",
        "//third_party:guava",
        "//third_party:jsr330_inject",
    ],
)

load("//tools:javadoc.bzl", "javadoc_library")

javadoc_library(
    name = "model-javadoc",
    srcs = [":model-srcs"],
    root_packages = ["dagger.model"],
    deps = [":model"],
)
