load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")
load("@bazel_tools//tools/build_defs/repo:git.bzl",
     "git_repository", "new_git_repository")
http_archive(
    name = "rules_foreign_cc",
    strip_prefix = "rules_foreign_cc-master",
    url = "https://github.com/bazelbuild/rules_foreign_cc/archive/master.zip",
)
load("@rules_foreign_cc//:workspace_definitions.bzl", "rules_foreign_cc_dependencies")
rules_foreign_cc_dependencies()
http_archive(
    name = "com_github_grpc_grpc",
    strip_prefix = "grpc-1.27.0",
    urls = ["https://github.com/grpc/grpc/archive/v1.27.0.tar.gz"],
)

load("@com_github_grpc_grpc//bazel:grpc_deps.bzl", "grpc_deps")

grpc_deps()

load("@com_github_grpc_grpc//bazel:grpc_extra_deps.bzl", "grpc_extra_deps")

grpc_extra_deps()
http_archive(
    # required by proto_library
    name = "com_google_protobuf",
    strip_prefix = "protobuf-3.13.0.1",
    urls = ["https://github.com/protocolbuffers/protobuf/archive/v3.13.0.1.zip"],
)

load("@com_google_protobuf//:protobuf_deps.bzl", "protobuf_deps")

protobuf_deps()
http_archive(
    name = "com_github_openssl",
    strip_prefix = "bazel_openssl-master",
    urls = ["https://github.com/jonnrb/bazel_openssl/archive/master.zip"],
)
http_archive(
    name = "boost",
    build_file = "@//:third_party/boost.BUILD",
    sha256 = "afff36d392885120bcac079148c177d1f6f7730ec3d47233aa51b0afa4db94a5",
    strip_prefix = "boost_1_74_0",
    urls = [
        "https://mirror.bazel.build/dl.bintray.com/boostorg/release/1.74.0/source/boost_1_74_0.tar.gz",
        "https://dl.bintray.com/boostorg/release/1.74.0/source/boost_1_74_0.tar.gz",
    ],
)
new_git_repository(
    name = "cpprest",
    build_file = "@//:third_party/cpprest/cpprest.BUILD",
    remote = "https://github.com/microsoft/cpprestsdk.git",
    commit = "18212a2a7967e12d740bfb957e500892b3463c88",
    init_submodules = True,
)