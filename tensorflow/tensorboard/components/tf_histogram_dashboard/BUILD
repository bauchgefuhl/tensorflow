package(default_visibility = ["//tensorflow:internal"])

load("@io_bazel_rules_closure//closure:defs.bzl", "web_library")
load("//tensorflow/tensorboard:defs.bzl", "tensorboard_ts_library")
load("//tensorflow/tensorboard:defs.bzl", "tensorboard_webcomponent_library")

licenses(["notice"])  # Apache 2.0

web_library(
    name = "tf_histogram_dashboard",
    srcs = [
        "tf-histogram-dashboard.html",
    ],
    path = "/tf-histogram-dashboard",
    deps = [
        "//tensorflow/tensorboard/components/tf_backend",
        "//tensorflow/tensorboard/components/tf_color_scale",
        "//tensorflow/tensorboard/components/tf_dashboard_common",
        "//tensorflow/tensorboard/components/tf_imports:lodash",
        "//tensorflow/tensorboard/components/vz_histogram_timeseries",
        "@org_polymer",
        "@org_polymer_iron_collapse",
        "@org_polymer_paper_icon_button",
        "@org_polymer_paper_styles",
    ],
)

filegroup(
    name = "all_files",
    srcs = glob(["**"]),
    tags = ["notsan"],
)

################################################################################
# MARKED FOR DELETION

tensorboard_webcomponent_library(
    name = "legacy",
    srcs = [
        "tf-histogram-dashboard.html",
        ":legacy_ts",
    ],
    destdir = "tf-histogram-dashboard",
    deps = [
        "//tensorflow/tensorboard/components/tf_backend:legacy",
        "//tensorflow/tensorboard/components/tf_dashboard_common:legacy",
        "//tensorflow/tensorboard/components/tf_imports_google:lib",
        "//tensorflow/tensorboard/components/vz_histogram_timeseries:legacy",
        "//third_party/javascript/polymer/v1/iron-collapse:lib",
        "//third_party/javascript/polymer/v1/paper-icon-button:lib",
        "//third_party/javascript/polymer/v1/paper-styles:lib",
        "//third_party/javascript/polymer/v1/polymer:lib",
    ],
)

# This is needed: components/BUILD seeks a legacy_ts rule in this package.
tensorboard_ts_library(
    name = "legacy_ts",
    srcs = [],
    deps_mgmt = "off",
    runtime = "nodejs",
)
