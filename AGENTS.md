# Repository agent guide

## Repository workflow and completion

This Go disk-usage app separates `cmd/gdu/` from analysis/UI packages. Use Go 1.24+ and the preferred tool version. CI runs `go test -v -covermode=count ./...` plus race coverage. `make build` produces the binary, `make test` needs gotestsum, and `make lint` needs golangci-lint.

Avoid default all/release/benchmark targets for focused checks: benchmarks may use sudo, alter CPU/cache settings, and scan home data. Use temporary directory fixtures. Private-disk scans and interactive deletion require an authorized target; never delete user data to demonstrate UI. Separate race/platform coverage from build evidence.

Continue the authorized change through relevant validation and repair of failures it causes; preserve unrelated work. Report checks actually run, commands only inspected, and exact missing prerequisites. Ask only when a material decision, missing authorization, or required input blocks progress; continue independent reversible work. Existing mandatory contribution and validation gates still apply.
