load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")
load("@bazel_tools//tools/build_defs/repo:git.bzl", 
  "git_repository", 
)

#
# Android
#

android_sdk_repository(
    name = "androidsdk",
    path = "/usr/local/share/android-sdk",
    api_level = 28,
    build_tools_version = "28.0.3"
)

android_ndk_repository(
    name = "androidndk",
    path = "/usr/local/share/android-ndk",  
    api_level = 28,
)

git_repository(
    name = "io_bazel_rules_kotlin",
    remote = "https://github.com/bazelbuild/rules_kotlin.git",
    commit = "4c71740a1b63b785fc90afd8d4d4d5bfda527107",
)

load("@io_bazel_rules_kotlin//kotlin:kotlin.bzl", "kotlin_repositories", "kt_register_toolchains")
kotlin_repositories()
kt_register_toolchains()

#
# Maven
#

git_repository(
    name = "rules_jvm_external",
    remote = "https://github.com/bazelbuild/rules_jvm_external.git",
    tag = "1.2",
)

load("@rules_jvm_external//:defs.bzl", "maven_install")
maven_install(
    artifacts = [
        "androidx.constraintlayout:constraintlayout:1.1.3",
        "androidx.annotation:annotation:1.0.2",
        "androidx.appcompat:appcompat:1.0.2",
        "androidx.core:core-ktx:1.0.1",
        "androidx.recyclerview:recyclerview:1.0.0",
        "com.airbnb.android:epoxy:3.3.1",
    ],
    repositories = [
        "https://jcenter.bintray.com/",
        "https://maven.google.com",
        "https://repo1.maven.org/maven2",
    ],
    fetch_sources = True,
)