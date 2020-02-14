config_setting(
    name = "k8-gcc4.8",
    values = {"cpu": "k8"},
)

config_setting(
    name = "k8-gcc5.4",
    define_values = {
     "gcc": "5.4",   
    },
    values = {"cpu": "k8"},
)

config_setting(
    name = "aarch64",
    values = {"cpu": "aarch64"},
)

filegroup(
    name = "empty",
    srcs = [],
)

cc_library(
    name = "pcl",
    srcs = select({
        ":k8-gcc4.8": glob(["lib/*.a*"]),
        ":k8-gcc5.4": glob(["lib-gcc5.4/*.a*"]),
        ":aarch64": glob(["lib-aarch64/*.a*"]),
        "//conditions:default": [":empty"]
    }),
   hdrs = glob([
        "include/pcl-1.7/pcl/*.h",
        "include/pcl-1.7/pcl/**/*.hpp",
        "include/pcl-1.7/pcl/**/**/*.hpp",
        "include/pcl-1.7/pcl/**/**/*.h",
        "include/pcl-1.7/pcl/**/**/**/*.hpp",
        "include/pcl-1.7/pcl/**/**/**/*.h",
    ]),
    includes = ["include/pcl-1.7"],
    visibility = ["//visibility:public"], 
    linkstatic = 1,
)
