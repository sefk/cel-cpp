# This package contains CEL evaluator tests (end-to-end, benchmark etc.)
#
#

package(default_visibility = ["//visibility:public"])

licenses(["notice"])  # Apache 2.0

exports_files(["LICENSE"])

cc_test(
    name = "benchmark_test",
    size = "small",
    srcs = [
        "benchmark_test.cc",
    ],
    copts = ["-std=c++14"],
    tags = ["manual"],
    deps = [
        ":request_context_cc_proto",
        "//eval/public:activation",
        "//eval/public:builtin_func_registrar",
        "//eval/public:cel_expr_builder_factory",
        "//eval/public:cel_expression",
        "//eval/public:cel_value",
        "@com_github_google_googlebench//:benchmark",
        "@com_github_google_googlebench//:benchmark_main",
        "@com_github_google_googletest//:gtest_main",
        "@com_google_absl//absl/base:core_headers",
        "@com_google_absl//absl/strings",
        "@com_google_googleapis//google/api/expr/v1alpha1:syntax_cc_proto",
        "@com_google_protobuf//:protobuf",
    ],
)

cc_test(
    name = "end_to_end_test",
    size = "small",
    srcs = [
        "end_to_end_test.cc",
    ],
    copts = ["-std=c++14"],
    deps = [
        "//eval/public:activation",
        "//eval/public:builtin_func_registrar",
        "//eval/public:cel_expr_builder_factory",
        "//eval/public:cel_expression",
        "//eval/public:cel_value",
        "//eval/testutil:test_message_cc_proto",
        "@com_github_google_googletest//:gtest_main",
        "@com_google_absl//absl/strings",
        "@com_google_googleapis//google/api/expr/v1alpha1:syntax_cc_proto",
        "@com_google_protobuf//:protobuf",
    ],
)

proto_library(
    name = "request_context_protos",
    srcs = [
        "request_context.proto",
    ],
)

cc_proto_library(
    name = "request_context_cc_proto",
    deps = [":request_context_protos"],
)
