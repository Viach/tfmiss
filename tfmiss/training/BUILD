package(default_visibility = ["//visibility:public"])
load("@protobuf_archive//:protobuf.bzl", "proto_gen")

py_library(
    name = "training",
    srcs = [
        # TODO: https://github.com/jasonwei20/eda_nlp + change case
        "__init__.py",
        "adapt.py",
        "bucket.py",
        "hparam.py",
    ],
    deps = [
         ":hparam_proto_py",
    ],
    srcs_version = "PY2AND3",
)

py_test(
    name = "adapt_test",
    srcs = ["adapt_test.py"],
    srcs_version = "PY2AND3",
    deps = [":training"],
)

py_test(
    name = "bucket_test",
    srcs = ["bucket_test.py"],
    srcs_version = "PY2AND3",
    deps = [":training"],
)

py_test(
    name = "hparam_test",
    srcs = ["hparam_test.py"],
    srcs_version = "PY2AND3",
    deps = [":training"],
)

proto_gen(
    name = "hparam_proto_py_genproto",
    srcs = [
        "hparam.proto",
    ],
    outs = [
        "hparam_pb2.py",
    ],
    gen_py = 1,
    # plugin = None,
    # plugin_language = "grpc",
    protoc = "@protobuf_archive//:protoc",
    # visibility = ["//visibility:public"],
    deps = ["@protobuf_archive//:protobuf_python_genproto"],
)

py_library(
    name = "hparam_proto_py",
    srcs = [
        "hparam_pb2.py",
    ],
    deps = [
        "@protobuf_archive//:protobuf_python"
    ],
)