load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

http_archive(
    name = "com_apt_itude_rules_pip",
    urls = ["https://github.com/ecosia/rules_pip/archive/99f5916ccfa2f185b839cabbd18cd0349b3e34f1.tar.gz"],
    strip_prefix = "rules_pip-99f5916ccfa2f185b839cabbd18cd0349b3e34f1",
    sha256 = "54d765b4963c45f85ebe39c5b2007b0e385476944a78f9576a7f800c8d87262b",
)

load("@com_apt_itude_rules_pip//rules:dependencies.bzl", "pip_rules_dependencies")

pip_rules_dependencies()

load("@com_apt_itude_rules_pip//rules:repository.bzl", "pip_repository")

pip_repository(
    name = "pip3",
    requirements = "//:requirements.txt",
    python_interpreter = "python3",
    # wheel_cache = "~/.cache/bazel/wheels",
    quiet = True,
)