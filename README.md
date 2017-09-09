# Minimal Bazel Scala Example

A simple example of a Scala multi-module project
configured to build using [Bazel](https://www.bazel.build).

Including:

* A main class `Runner`
* A library `Foo` which depends on library `bar`
* An external dependency (ScalaTest)
* A test `RunnerTest`

Feedback / pull requests welcome.

## Running Test

    bazel test //...

## Running

    bazel run runner

Or, once built using Bazel, call the generated run-script:

    bazel-bin/Runner

## Review the dependency graph

    bazel query  --nohost_deps --noimplicit_deps 'deps(//...)' --output graph > graph.dot
    dot graph.dot -Tpng -o graph.png

![Graph](graph.png)

# Reference

https://github.com/bazelbuild/rules_scala