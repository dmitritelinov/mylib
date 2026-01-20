**NOTE: WORK IN PROGRESS IMPLEMENTATION BASED ON PROVIDED REQUIREMENTS**

# mylib
C++ library with CI/CD

# What's inside
## Tiny library
**src/mylib.cpp** - library implementation (sum, multiply)

**include/mylib.h** - Library header files

## GoogleTest unit tests
**tests/test_mylib.cpp** - GoogleTest unit tests

## Use CMake
**CMakeLists.txt** - Make build with install rules

## Conan 2 packaging
**conanfile.py** - Conan 2 recipe with multi-platform support which includes function for versioning `<X.Y.Z>-dev-<short-sha>`

## Conan 2 profiles
**profiles/linux-gcc** - Linux profile

**profiles/macos-clang** - MacOS profile

**profiles/windows-msv**c - Windows profile

## GitHub Actions Workflows
**setup-branch-protection.yml** - Automated branch protection configuration

**pr-verify.yml** - Comprehensive PR validation which includes:
* linting (format)
* build in parallel for Linux, MacOS and Windows
* unit tests with GoogleTest
* dependency lockfiles
* integration tests based on PR **label: verify** which uploads built RC to Artifactory once PR is labelled
* versioning `<X.Y.Z>-dev-<short-sha>`
* all common CI tasks extracted to [shared-cicd-actions](https://github.com/dmitritelinov/shared-cicd-actions) repository and reused in this workflow

