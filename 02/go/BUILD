load("@io_bazel_rules_go//go:def.bzl", "go_binary", "go_test", "go_source")

go_library(
    name = "go_default_library",
    srcs = glob(["src/main/**/*.go"]),
    importpath = "gitlab.com/lopnor/src/main/src/main",
    visibility = ["//visibility:private"],
    deps = [
        "@com_github_flimzy_kivik//:go_default_library",
        "@com_github_go_kivik_couchdb//:go_default_library",
        "@go_dockerclient//:go_default_library",
    ],
)

go_binary(
    name = "main",
    embed = [":go_default_library"],
    visibility = ["//visibility:public"],
)

genrule(
    name = "normalised_binary",
    srcs = [":some_binary"],
    outs = ["the_binary"],
    cmd = "cp $(SRCS) $@",
)

sh_test(
    name = "executable_name",
    size = "small",
    srcs = ["name_test.sh"],
    data = [ ":normalised_binary" ],
)

