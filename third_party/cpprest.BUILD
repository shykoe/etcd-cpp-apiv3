# -*- bazel -*-
licenses(["notice"])
exports_files(["LICENSES"])

load("@rules_foreign_cc//tools/build_defs:cmake.bzl", "cmake_external")

filegroup(name = "all", srcs = glob(["**"]), visibility = ["//visibility:private"])

cmake_external(
    name = "cpprest",
    deps = [
        # note: really openssl, boringssl doesn't work here
        "@boringssl//:ssl",
        "@//third_party/boost:boost_asio",
    ],
    cache_entries = {
        "WERROR": "OFF",
        "CMAKE_POSITION_INDEPENDENT_CODE:BOOL": "ON",
        "CMAKE_POSITION_INDEPENDENT_CODE": "ON",
        "POSITION_INDEPENDENT_CODE": "ON",
        "CMAKE_BUILD_SHARED_LIBS": "OFF",
        "BUILD_SHARED_LIBS": "OFF",
        "BUILD_TESTS": "OFF",
        "BUILD_SAMPLES": "OFF",
        "Boost_USE_STATIC_LIBS": "ON",
        "OPENSSL_INCLUDE_DIR": "$EXT_BUILD_DEPS/include",
        "OPENSSL_LDFLAGS": "-L$EXT_BUILD_DEPS/lib -lpthread -ldl -lcrypto -lssl",
    },
    lib_source = ":all",
    out_lib_dir = "lib64",
    static_libraries = ["libcpprest.a"],
    visibility = ["//visibility:public"],
)
