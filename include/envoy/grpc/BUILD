licenses(["notice"])  # Apache 2

load(
    "//bazel:envoy_build_system.bzl",
    "envoy_cc_library",
    "envoy_package",
)

envoy_package()

envoy_cc_library(
    name = "async_client_interface",
    hdrs = ["async_client.h"],
    deps = [
        ":status",
        "//include/envoy/common:optional",
        "//include/envoy/http:header_map_interface",
        "//include/envoy/tracing:http_tracer_interface",
        "//source/common/protobuf",
    ],
)

envoy_cc_library(
    name = "async_client_manager_interface",
    hdrs = ["async_client_manager.h"],
    deps = [
        ":async_client_interface",
        "//include/envoy/stats:stats_interface",
        "@envoy_api//envoy/api/v2/core:grpc_service_cc",
    ],
)

envoy_cc_library(
    name = "google_async_site_interface",
    hdrs = ["google_async_site.h"],
    external_deps = ["grpc"],
    deps = ["@envoy_api//envoy/api/v2/core:grpc_service_cc"],
)

envoy_cc_library(
    name = "status",
    hdrs = ["status.h"],
)
