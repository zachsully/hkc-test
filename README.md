# HKC Testing Framework #
---

HKC compiles Hakaru programs to C. Programs stored in "src" directory are
starting points for tests. In the future, output programs can be stored there
as well.

## HKC-Test dependencies

HKC generated code depends on the boehm garbage collector, a C compiler, and
the Haskell dependencies listed in the cabal file.

## Running the tests

After building the test program with `cabal build`, run the test suite with the
following commands

```
dist/build/hkc-test/hkc-test <hkc-exe> <c compiler>
```

It will generate a directory `build` which will contain `hkc.log`, `cc.log`, and
the subdirectories `build/sea` and `build/bin`. The two log files will contain
the error messages generated by any of the tests. The subdirectories will
contain the output files of compiling with `hkc` and `cc` respectively.

## Adding tests

To add a test, simply add a new Hakaru file to `tests/hakaru/<testname>.hk`. To
specify the test's input, create a file `tests/input/<testname>.in` (unless the
program does not take arguments). To specify the test's correct output, create a
file `tests/output/<testname>.out`.
