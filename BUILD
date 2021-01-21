package(default_visibility = ["//visibility:public"])

load("@rules_proto//proto:defs.bzl", "proto_library")
load("@rules_cc//cc:defs.bzl", "cc_binary", "cc_library", "cc_proto_library")
load("@com_github_grpc_grpc//bazel:cc_grpc_library.bzl", "cc_grpc_library")
proto_library(
    name = "g_protos",
    srcs = glob(["proto/google/api/*.proto"]),
    deps = ["@com_google_protobuf//:descriptor_proto"],
    strip_import_prefix = "proto",
)
proto_library(
    name = "gogo_protos",
    srcs = glob(["proto/gogoproto/gogo.proto"]),
    deps = ["@com_google_protobuf//:descriptor_proto"],
    strip_import_prefix = "proto",
)
proto_library(
    name = "protos",
    srcs = glob(["proto/*.proto"]),
    deps = [
        ":g_protos",
        ":gogo_protos",
        "@com_google_protobuf//:descriptor_proto"
    ],
    # strip_import_prefix = "proto",
)