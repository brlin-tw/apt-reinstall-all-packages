# apt-reinstall-all-packages

Re-install all packages on an APT-managed system, without changing (much) state.

<https://gitlab.com/brlin/apt-reinstall-all-packages>  
[![The GitLab CI pipeline status badge of the project's `main` branch](https://gitlab.com/brlin/apt-reinstall-all-packages/badges/main/pipeline.svg?ignore_skipped=true "Click here to check out the comprehensive status of the GitLab CI pipelines")](https://gitlab.com/brlin/apt-reinstall-all-packages/-/pipelines) [![GitHub Actions workflow status badge](https://github.com/brlin-tw/apt-reinstall-all-packages/actions/workflows/check-potential-problems.yml/badge.svg "GitHub Actions workflow status")](https://github.com/brlin-tw/apt-reinstall-all-packages/actions/workflows/check-potential-problems.yml) [![pre-commit enabled badge](https://img.shields.io/badge/pre--commit-enabled-brightgreen?logo=pre-commit&logoColor=white "This project uses pre-commit to check potential problems")](https://pre-commit.com/) [![REUSE Specification compliance badge](https://api.reuse.software/badge/gitlab.com/brlin/apt-reinstall-all-packages "This project complies to the REUSE specification to decrease software licensing costs")](https://api.reuse.software/info/gitlab.com/brlin/apt-reinstall-all-packages)

## Features

The following are the notable features of this product:

* Will not affect the "automatically installed" state of the packages, allow unused packages to be automatically removed when not used.
* Support fast-forwarding to start from user specified package, allowing the user to resume an interrupted process.
* Support re-installing user-specified subset of packages instead, useful for retrying the re-installation.

## Usage

This section documents the usage of this utility:

1. Download the product release archive from [the Releases page](https://gitlab.com/brlin/apt-reinstall-all-packages/-/releases).
1. Extract the product release archive using your preferred archive manipulation application, or, run the following command in a text terminal application:

    ```bash
    tar_opts=(
        # Extract the specified archive
        --extract
        --file /path/to/apt-reinstall-all-packages-X.Y.Z.tar.gz

        # Display files that are extracted
        --verbose
    )
    tar "${tar_opts[@]}"
    ```

1. Launch a text terminal application(if it is not launched already).
1. Refer [the Environment variables that can customize the utility's behaviors](#environment-variables-that-can-customize-the-utilitys-behaviors) and [the Internal variables that can customize the utility's behaviors](#internal-variables-that-can-customize-the-utilitys-behaviors) section for ways to customize the utility's behaviors.
1. Run the utility program by running the following command _as root_:

    ```bash
    /path/to/apt-reinstall-all-packages-X.Y.Z/apt-reinstall-all-packages _subset packages_...
    ```

   The _subset packages_ program parameters are only needed if you prefer to only re-install these subset packages, if omitted all non-excluded packages are re-installed.

### Environment variables that can customize the utility's behaviors

This section documents the environment variables that can customize the utility's behaviors according to your needs:

#### START_FROM_PACKAGE

Specify the name of the package to start the re-installation from.  This is useful for resuming an interrupted reinstallation session.

**Default value:** (null): Start from the first installed package.

### Internal variables that can customize the utility's behaviors

This section documents the internal variables that can customize the utility's behaviors according to your needs.  You need to edit the utility program using a plaintext editor to change the definition of the variables.

#### EXCLUDED_PACKAGE_NAME_REGEXES

This array variable holds the POSIX extended regular expression patterns to match the name of the packages you don't want to run the re-installation.  This may be useful for packages that don't matter much from being corrupted like documentation, etc.

**Default value:** (null): None is excluded.

Refer the existing program comment for some examples.

## Note

* This utility will always install the latest version available in the software archive, it WILL NOT preserve the original version installed in the system.

## References

The following self/third-party materials are referenced during the development of this project:

* [brlin-tw/apt-get_reinstall-all: 這是讓 apt-get 強制重新安裝系統目前已經安裝的所有軟體包的程式](https://github.com/brlin-tw/apt-get_reinstall-all)  
  Previous implementation.
* [Reinstalling all Debian packages - Unix & Linux Stack Exchange](https://unix.stackexchange.com/questions/79125/reinstalling-all-debian-packages)  
  Existing solutions to the same problem.
* dpkg(1) manual page  
  For information about the dpkg package states.
* dpkg-query(1) manual page  
  For querying all the installed packages in the system.
* [bash - Redirect all subsequent commands' stderr using exec - Unix & Linux Stack Exchange](https://unix.stackexchange.com/questions/61931/redirect-all-subsequent-commands-stderr-using-exec)  
  Explains how to log script output from with-in the shell script.
* apt-mark(8) manual page  
  For querying the automatically/manually installed status of a installed package.
* [`Source` — List of fields — Control files and their fields — Debian Policy Manual](https://www.debian.org/doc/debian-policy/ch-controlfields.html#s-f-source)  
  Explains the character set that composes a Debian source(and binary) package names.
* debconf(7) manual page  
  Explains how to avoid debconf's prompts to be shown during installation.

## Licensing

Unless otherwise noted(individual file's header/[REUSE DEP5](.reuse/dep5)), this product is licensed under [the 4.0 International version of the Creative Commons Attribution-ShareAlike license](https://creativecommons.org/licenses/by-sa/4.0/), or any of its more recent versions of your preference.

This work complies to the [REUSE Specification](https://reuse.software/spec/), refer the [REUSE - Make licensing easy for everyone](https://reuse.software/) website for info regarding the licensing of this product.
