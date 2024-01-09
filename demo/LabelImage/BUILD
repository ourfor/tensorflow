load("@build_bazel_rules_apple//apple:macos.bzl", "macos_command_line_application")
# load("@rules_xcodeproj//:rules.bzl", "xcodeproj")
load(
    "@rules_xcodeproj//xcodeproj:defs.bzl",
    "top_level_target",
    "xcodeproj",
)

package(default_visibility = [
    "//examples:__subpackages__",
])

licenses(["notice"])

RELEASE_COPTS = [
    # Enables language-specific warnings for Objective-C, Objective-C++, C, and C++.
    "-Wall",
    # Warns if functions, variables, and types marked with the deprecated attribute are being used.
    "-Wdeprecated-declarations",
    # Warns for errors in documentation.
    "-Wdocumentation",
    # Turns all warnings into errors.
    "-Werror",
    # Enables extra warning flags that are not enabled by -Wall.
    "-Wextra",
    # Warns if a global function is defined without a previous prototype declaration.
    "-Wmissing-prototypes",
    # From -Wextra. Disables warning when signed value is converted to unsigned value during comparison.
    "-Wno-sign-compare",
    # From -Wextra. Disables warning for unused parameters, which are common in delegate methods and block callbacks.
    "-Wno-unused-parameter",
    # Warns if a global or local variable or type declaration shadows another variable, parameter, type, class member, or instance variable.
    "-Wshadow",
    # Warns if a function is declared or defined without specifying the argument types. For a block with no args, use (void) instead of ().
    "-Wstrict-prototypes",
    # Warns if an @selector() expression is encountered with a method name that hasn't been defined yet.
    "-Wundeclared-selector",
    # Turn off warnings for headers not part of TensorFlow Lite Objective-C API.
    "--system-header-prefix=tensorflow/lite/c/",
]

# Compiler flags for building test libraries.
TEST_COPTS = RELEASE_COPTS + [
    # From -Wall. Disables warning when passing nil to a callee that requires a non-null argument.
    "-Wno-nonnull",
    # Disables warning when a global or local variable or type declaration shadows another.
    "-Wno-shadow",
]

xcodeproj(
    name = "xcodeproj",
    build_mode = "bazel",
    project_name = "LabelImage",
    tags = ["manual"],
    top_level_targets = [
        "//tensorflow/lite/examples/label_image:label_image",
    ],
)
