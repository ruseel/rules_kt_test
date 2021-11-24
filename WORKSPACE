load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

# rules_jvm_external
RULES_JVM_EXTERNAL_TAG = "4.1"
RULES_JVM_EXTERNAL_SHA = "f36441aa876c4f6427bfb2d1f2d723b48e9d930b62662bf723ddfb8fc80f0140"

http_archive(
    name = "rules_jvm_external",
    strip_prefix = "rules_jvm_external-%s" % RULES_JVM_EXTERNAL_TAG,
    sha256 = RULES_JVM_EXTERNAL_SHA,
    url = "https://github.com/bazelbuild/rules_jvm_external/archive/%s.zip" % RULES_JVM_EXTERNAL_TAG,
)

# rules_java
http_archive(
    name = "rules_java",
    url = "https://github.com/bazelbuild/rules_java/releases/download/4.0.0/rules_java-4.0.0.tar.gz",
    sha256 = "34b41ec683e67253043ab1a3d1e8b7c61e4e8edefbcad485381328c934d072fe",
)
load("@rules_java//java:repositories.bzl", "rules_java_dependencies", "rules_java_toolchains")
rules_java_dependencies()
rules_java_toolchains()

# kotlin
rules_kotlin_version = "v1.5.0-beta-4"
rules_kotlin_sha = "6cbd4e5768bdfae1598662e40272729ec9ece8b7bded8f0d2c81c8ff96dc139d"
http_archive(
    name = "io_bazel_rules_kotlin",
    sha256 = rules_kotlin_sha,
    type = "tgz",
    urls = [
        "https://github.com/bazelbuild/rules_kotlin/releases/download/%s/rules_kotlin_release.tgz" % rules_kotlin_version,
    ],
)

KOTLIN_VERSION = "1.4.20"
KOTLINC_RELEASE_SHA = "11db93a4d6789e3406c7f60b9f267eba26d6483dcd771eff9f85bb7e9837011f"
KOTLINC_RELEASE = {
    "urls": [
        "https://github.com/JetBrains/kotlin/releases/download/v{v}/kotlin-compiler-{v}.zip".format(v = KOTLIN_VERSION),
    ],
    "sha256": KOTLINC_RELEASE_SHA,
}
load("@io_bazel_rules_kotlin//kotlin:repositories.bzl", "kotlin_repositories")
kotlin_repositories()

register_toolchains("//kotlin:kotlin_toolchain")
