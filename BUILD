load('@build_bazel_rules_nodejs//:index.bzl', 'nodejs_binary')

nodejs_binary(
    name = 'main',
    entry_point = 'index.js',
    data = [
        '@npm//mongodb-stitch',
        '@npm//@okta/okta-auth-js'
    ]
)
