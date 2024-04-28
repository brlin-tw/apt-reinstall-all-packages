# apt-reinstall-all-packages

Re-install all packages on an APT-managed system, without changing (much) state.

<https://gitlab.com/brlin/apt-reinstall-all-packages>  
[![The GitLab CI pipeline status badge of the project's `main` branch](https://gitlab.com/brlin/apt-reinstall-all-packages/badges/main/pipeline.svg?ignore_skipped=true "Click here to check out the comprehensive status of the GitLab CI pipelines")](https://gitlab.com/brlin/apt-reinstall-all-packages/-/pipelines) [![GitHub Actions workflow status badge](https://github.com/brlin-tw/apt-reinstall-all-packages/actions/workflows/check-potential-problems.yml/badge.svg "GitHub Actions workflow status")](https://github.com/brlin-tw/apt-reinstall-all-packages/actions/workflows/check-potential-problems.yml) [![pre-commit enabled badge](https://img.shields.io/badge/pre--commit-enabled-brightgreen?logo=pre-commit&logoColor=white "This project uses pre-commit to check potential problems")](https://pre-commit.com/) [![REUSE Specification compliance badge](https://api.reuse.software/badge/gitlab.com/brlin/apt-reinstall-all-packages "This project complies to the REUSE specification to decrease software licensing costs")](https://api.reuse.software/info/gitlab.com/brlin/apt-reinstall-all-packages)

## Reference

The following self/third-party materials are referenced during the development of this project:

* [brlin-tw/apt-get_reinstall-all: 這是讓 apt-get 強制重新安裝系統目前已經安裝的所有軟體包的程式](https://github.com/brlin-tw/apt-get_reinstall-all)  
  Previous implementation.
* [Reinstalling all Debian packages - Unix & Linux Stack Exchange](https://unix.stackexchange.com/questions/79125/reinstalling-all-debian-packages)  
  Existing solutions to the same problem.
* dpkg(1)  
  For information about the dpkg package states.
* dpkg-query(1)  
  For querying all the installed packages in the system.

## Licensing

Unless otherwise noted(individual file's header/[REUSE DEP5](.reuse/dep5)), this product is licensed under [the 4.0 International version of the Creative Commons Attribution-ShareAlike license](https://creativecommons.org/licenses/by-sa/4.0/), or any of its more recent versions of your preference.

This work complies to the [REUSE Specification](https://reuse.software/spec/), refer the [REUSE - Make licensing easy for everyone](https://reuse.software/) website for info regarding the licensing of this product.
