load("@rules_cc//cc:defs.bzl", "cc_binary", "cc_library")
load("@rules_foreign_cc//tools/build_defs:cmake.bzl", "cmake_external")

cc_binary(
    name = "matrix_basic",
    srcs = ["matrix_basic.cc"],
    deps = ["@eigen"]
)

cc_binary(
    name = "hw1",
    srcs = ["hw1.cpp"],
    deps = ["rasterizer"]
)

cc_binary(
    name = "hw2",
    srcs = ["hw2.cpp"],
    deps = ["rasterizer"]
)

cc_library(
    name = "rasterizer",
    srcs = ["rasterizer.cpp"],
    hdrs = ["rasterizer.hpp"],
    deps = ["@eigen", "opencv", "triangle"]
)


cmake_external(
    name = "opencv",
    cmake_options = [
        "-GNinja",
        "-DBUILD_LIST=core,highgui,imgcodecs,imgproc",
    ],
    lib_source = "@opencv//:all",
    make_commands = [
        "ninja",
        "ninja install",
    ],
    out_include_dir = "include/opencv4",
    shared_libraries = [
        "libopencv_core.so",
        "libopencv_highgui.so",
        "libopencv_imgcodecs.so",
        "libopencv_imgproc.so",
    ],
    visibility = ["//visibility:public"],
)