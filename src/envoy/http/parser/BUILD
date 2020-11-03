load(
    "@envoy//bazel:envoy_build_system.bzl",
    "envoy_cc_library",
)

licenses(["notice"])  # Apache 2

envoy_cc_library(
    name = "http_parser",
    srcs = [
        "http_parser.c",
        "http_parser.h",
    ],
    hdrs = ["http_parser.h"],
    # This compiler flag is set to an arbtitrarily high number so
    # as to effectively disables the http_parser header limit, as
    # we do our own checks in the conn manager and codec.
    copts = ["-DHTTP_MAX_HEADER_SIZE=0x2000000", "-DHTTP_PARSER_STRICT=0"],
    includes = ["."],
    repository = "@envoy",
    visibility = ["//visibility:public"],
)
