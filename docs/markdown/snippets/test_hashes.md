## `meson test --hash-record` and `--hash-changed`

`meson test --hash-record` records a hash for each selected test which
runs a built program, without running any tests. The hash covers the
contents of every file on the test command line, including the
program, any exe wrapper and `--wrapper`, along with the other
arguments.

`meson test --hash-changed` then runs only the selected tests whose
hash is different or missing, along with any tests which don't run a
built program. This is useful for continuous integration, where the
tests of a base commit can be skipped when testing a change.
