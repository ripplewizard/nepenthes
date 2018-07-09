# load(
#     "@build_bazel_rules_nodejs//:defs.bzl",
#     "jasmine_node_test",
#     "nodejs_binary",
# )

# filegroup(
#     name = "node_modules",
#     srcs = glob([
#         "node_modules/**/*",
#     ]),
# )


# nodejs_binary(
#     name = "demo",
#     data = [
#         "@//:node_modules",
#         "index.js"
#     ],
#     # entry_point = "demo_nodejs_bazel/index.js",
#     args = ["--node_options=--expose-gc"],
# )

package(default_visibility = ["//visibility:public"])

load("@org_pubref_rules_node//node:rules.bzl", "node_binary", "node_module", "node_test")


node_module(
    name = "lib",
    main = "index.js",
)

node_binary(
    name = "demo",
    entrypoint = ":lib",
)