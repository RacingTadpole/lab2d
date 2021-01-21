# Description:
#   Build rule for Python and Numpy.
#   This rule works for Debian and Ubuntu. Other platforms might keep the
#   headers in different places.

cc_library(
    name = "python_headers",
    hdrs = select(
        {
            "@bazel_tools//tools/python:PY2": glob(["python2.7/*.h"]),
            "@bazel_tools//tools/python:PY3": glob(["3.8/Headers/**/*.h"]),
        },
        no_match_error = "Internal error, Python version should be one of PY2 or PY3",
    ),
    includes = select(
        {
            "@bazel_tools//tools/python:PY2": ["python2.7"],
            "@bazel_tools//tools/python:PY3": ["3.8/Headers"],
        },
        no_match_error = "Internal error, Python version should be one of PY2 or PY3",
    ),
    visibility = ["//visibility:public"],
)
