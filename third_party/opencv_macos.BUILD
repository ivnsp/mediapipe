# Description:
#   OpenCV libraries for video/image processing on MacOS

licenses(["notice"])  # BSD license

exports_files(["LICENSE"])

load("@bazel_skylib//lib:paths.bzl", "paths")

# The path to OpenCV is a combination of the path set for "macos_opencv"
# in the WORKSPACE file and the prefix here.
PREFIX = "opt/local/lib/opencv4"

cc_library(
    name = "opencv",
    srcs = glob(
        [
            paths.join(PREFIX, "libopencv_core.dylib"),
            paths.join(PREFIX, "libopencv_calib3d.dylib"),
            paths.join(PREFIX, "libopencv_features2d.dylib"),
            paths.join(PREFIX, "libopencv_highgui.dylib"),
            paths.join(PREFIX, "libopencv_imgcodecs.dylib"),
            paths.join(PREFIX, "libopencv_imgproc.dylib"),
            paths.join(PREFIX, "libopencv_video.dylib"),
            paths.join(PREFIX, "libopencv_videoio.dylib"),
        ],
    ),
    hdrs = glob([paths.join(PREFIX, "include/opencv2/**/*.h*")]),
    includes = [paths.join(PREFIX, "include/")],
    linkstatic = 1,
    visibility = ["//visibility:public"],
)
