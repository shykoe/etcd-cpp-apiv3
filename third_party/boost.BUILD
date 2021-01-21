load("@rules_foreign_cc//tools/build_defs:boost_build.bzl", "boost_build")

package(default_visibility = ["//visibility:private"])
filegroup(name = "all", srcs = glob(["**"]), visibility = ["//visibility:private"])

boost_build(
    name = "boost",
    lib_source = ":all",
    defines = ["BOOST_ASIO_SEPARATE_COMPILATION"],
    static_libraries = [
        "libboost_atomic.a",
        "libboost_chrono.a",
        "libboost_date_time.a",
        "libboost_filesystem.a",
        "libboost_locale.a",
        "libboost_random.a",
        "libboost_regex.a",
        "libboost_system.a",
        "libboost_thread.a",
    ],
    deps = [
        "@boringssl//:ssl"
    ],
    user_options = [
        "--with-atomic",
        "--with-chrono",
        "--with-date_time",
        "--with-filesystem",
        "--with-locale",
        "--with-random",
        "--with-regex",
        "--with-system",
        "--with-thread",
        "link=static",
        "cflags=-fPIC",
        "cxxflags=-fPIC",
        "linkflags=-fPIC",
    ],
    visibility = ["//visibility:public"],
)

