---
title: "Development"
description: "Each commit into Nelson Github repository starts a continuous integration process based on Jenkins"
---

# Development

Each commit into Nelson Github repository starts a continuous integration process based on Jenkins:
![Jenkins screenshot](images/Jenkins.png "Nelson Jenkins")

Github actions used to check each commits on Windows, Linux and MacOs:
![Github actions CI screenshot](images/github_actions.png "Github actions CI")
[Github actions CI](https://github.com/nelson-lang/nelson/actions)

Each build process executes all unitary tests and non-regression tests under all supported platforms:
![xUnit Result](images/xUnit.png "xUnit")

![test_run capture](images/test_run.png "test_run")

[Back to features](features.md)
