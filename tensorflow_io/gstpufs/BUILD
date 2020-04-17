load(
    "//third_party/tensorflow:tensorflow.bzl",
    "tf_copts",
)

licenses(["notice"])

exports_files([
    "LICENSE",
    "ACKNOWLEDGMENTS",
    # The leakr files are used by //third_party/cloud_tpu and
    # //third_party/tensorboard/google:copybara_config_test.
    "leakr_badwords.dic",
    "leakr_badfiles.dic",
    "leakr_file_type_recipe.ftrcp",
])

cc_library(
    name = "gs_tpu_file_system",
    srcs = ["gs_tpu_file_system.cc"],
    hdrs = ["gs_tpu_file_system.h"],
    copts = tf_copts(),
    linkstatic = 1,  # Needed since alwayslink is broken in bazel b/27630669
    deps = [
        "@com_google_absl//absl/memory",
        "@local_config_tf//:libtensorflow_framework",
        "@local_config_tf//:tf_header_lib",
    ],
    alwayslink = 1,
)
