load("//tensorflow:strict.default.bzl", "py_strict_library")
load("//tensorflow:tensorflow.default.bzl", "tf_py_test")

package(
    # copybara:uncomment default_applicable_licenses = ["//tensorflow:license"],
    licenses = ["notice"],
)

py_strict_library(
    name = "api",
    srcs = ["api.py"],
    visibility = ["//tensorflow:__subpackages__"],
    deps = [
        ":conversion",
        "//tensorflow/python/autograph/converters:asserts",
        "//tensorflow/python/autograph/converters:break_statements",
        "//tensorflow/python/autograph/converters:call_trees",
        "//tensorflow/python/autograph/converters:conditional_expressions",
        "//tensorflow/python/autograph/converters:continue_statements",
        "//tensorflow/python/autograph/converters:control_flow",
        "//tensorflow/python/autograph/converters:directives",
        "//tensorflow/python/autograph/converters:functions",
        "//tensorflow/python/autograph/converters:lists",
        "//tensorflow/python/autograph/converters:logical_expressions",
        "//tensorflow/python/autograph/converters:return_statements",
        "//tensorflow/python/autograph/converters:slices",
        "//tensorflow/python/autograph/converters:variables",
        "//tensorflow/python/autograph/core:ag_ctx",
        "//tensorflow/python/autograph/core:converter",
        "//tensorflow/python/autograph/core:function_wrappers",
        "//tensorflow/python/autograph/core:unsupported_features_checker",
        "//tensorflow/python/autograph/lang:special_functions",
        "//tensorflow/python/autograph/operators",
        "//tensorflow/python/autograph/pyct",
        "//tensorflow/python/autograph/pyct/static_analysis:activity",
        "//tensorflow/python/autograph/pyct/static_analysis:reaching_definitions",
        "//tensorflow/python/autograph/utils:__init__",
        "//tensorflow/python/autograph/utils:ag_logging",
        "//tensorflow/python/eager/polymorphic_function:tf_method_target",
        "//tensorflow/python/framework:errors",
        "//tensorflow/python/util:tf_decorator",
        "//tensorflow/python/util:tf_export",
        "//tensorflow/python/util:tf_stack",
    ],
)

py_strict_library(
    name = "conversion",
    srcs = ["conversion.py"],
    visibility = ["//tensorflow:__subpackages__"],
    deps = [
        "//tensorflow/python/autograph/core:config",
        "//tensorflow/python/autograph/pyct",
        "//tensorflow/python/autograph/utils:ag_logging",
        "//tensorflow/python/eager/polymorphic_function:tf_method_target",
        "//tensorflow/python/util:tf_inspect",
    ],
)

tf_py_test(
    name = "api_test",
    srcs = ["api_test.py"],
    python_version = "PY3",
    srcs_version = "PY3",
    deps = [
        ":api",
        ":conversion",
        "//tensorflow/python:client_testlib",
        "//tensorflow/python:math_ops",
        "//tensorflow/python:variables",
        "//tensorflow/python/autograph/core:ag_ctx",
        "//tensorflow/python/autograph/core:converter",
        "//tensorflow/python/autograph/core:test_lib",
        "//tensorflow/python/autograph/pyct",
        "//tensorflow/python/autograph/utils:ag_logging",
        "//tensorflow/python/data/ops:dataset_ops",
        "//tensorflow/python/eager:def_function",
        "//tensorflow/python/framework:_errors_test_helper",
        "//tensorflow/python/framework:constant_op",
        "//tensorflow/python/framework:errors",
        "//tensorflow/python/framework:ops",
        "//tensorflow/python/framework:test_lib",
        "//tensorflow/python/util:function_utils",
        "//tensorflow/python/util:tf_decorator",
        "//third_party/py/numpy",
    ],
)

tf_py_test(
    name = "conversion_test",
    srcs = ["conversion_test.py"],
    deps = [
        ":api",
        ":conversion",
        "//tensorflow/python:client_testlib",
        "//tensorflow/python/autograph/core:config",
        "//tensorflow/python/autograph/core:converter",
        "//tensorflow/python/autograph/impl/testing:pybind_for_testing",
        "//tensorflow/python/autograph/utils:__init__",
        "//tensorflow/python/eager:function",
        "//tensorflow/python/framework:constant_op",
    ],
)
