# NwauCore

`NwauCore` is a small Julia wrapper for the MCHS/NWAU command boundary.
It validates the input CSV, assembles the CLI invocation, and returns the generated output path.
The package does not implement the calculation formulas itself.

## Purpose

`NWAU` refers to the National Weighted Activity Unit workflow used by the surrounding tooling.
`Core` is used here to indicate that this package is only the thin orchestration layer around that workflow, not the full calculator implementation.

## Minimal usage

```julia
using NwauCore

output_csv = calculate("acute";
    input_csv = "path/to/input.csv",
    output_csv = "path/to/output.csv",
    year = 2025,
    params_dir = "path/to/params",
)
```

Convenience wrappers are also available:

- `calculate_acute`
- `calculate_ed`
- `calculate_non_admitted`
