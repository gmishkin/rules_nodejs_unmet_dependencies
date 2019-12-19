workspace(
    name = "info_amsa_rules_nodejs_unmet_dependency",
    managed_directories = {"@npm": ["node_modules"]}
)
load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_file", "http_archive")

http_archive(
    name = "build_bazel_rules_nodejs",
    sha256 = "a54b2511d6dae42c1f7cdaeb08144ee2808193a088004fc3b464a04583d5aa2e",
    urls = ["https://github.com/bazelbuild/rules_nodejs/releases/download/0.42.3/rules_nodejs-0.42.3.tar.gz"],
)
load("@build_bazel_rules_nodejs//:index.bzl", "node_repositories", "npm_install")

NODE_VERSION = '12.13.0'
node_repositories(
    node_version = NODE_VERSION,
    node_repositories = {
        "%s-darwin_amd64" % (NODE_VERSION): ("node-v%s-darwin-x64.tar.gz" % (NODE_VERSION), "node-v%s-darwin-x64" % (NODE_VERSION), "49a7374670a111b033ce16611b20fd1aafd3296bbc662b184fe8fb26a29c22cc"),
        "%s-linux_amd64" % (NODE_VERSION): ("node-v%s-linux-x64.tar.xz" % (NODE_VERSION), "node-v%s-linux-x64" % (NODE_VERSION), "7a57ef2cb3036d7eacd50ae7ba07245a28336a93652641c065f747adb2a356d9"),
        "%s-windows_amd64" % (NODE_VERSION): ("node-v%s-win-x64.zip" % (NODE_VERSION), "node-v%s-win-x64" % (NODE_VERSION), "6f920cebeecb4957b4ef0def6d9b04c49d4582864f8d1a207ce8d0665865781a"),
    },
    node_urls = ["https://nodejs.org/dist/v{version}/{filename}"],
    package_json = ["//:package.json"]
)

# JavaScript dependencies
npm_install(
    name = 'npm',
    package_json = '//:package.json',
    package_lock_json = '//:package-lock.json'
)
