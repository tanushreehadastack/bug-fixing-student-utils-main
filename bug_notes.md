# Bug Notes

| Bug | Evidence / Failed Test | Cause | Fix |
|---|---|---|---|
| Average | `135.0` instead of `90.0` for `[80, 90, 100]`; `ZeroDivisionError` for `[40]`; `120.0` instead of `60.0` for `[50, 70]` | Dividing by `len(marks) - 1` | Divide by `len(marks)` |
| Pass boundary | `is_passing(40)` returned `False` | Used `>` instead of `>=` | Use `>= PASS_MARK` |
| Distinction | `get_grade(95)` returned `"First"` | `>= 60` was checked before `>= 90`, so the Distinction branch was unreachable | Check `>= 90` first |

## Why 135 instead of 90
Total of `[80, 90, 100]` is 270. The buggy code divided by `3 - 1 = 2`, giving `135`.
The correct average divides by the real count: `270 / 3 = 90`.
The same denominator bug makes `len([40]) - 1 = 0`, which causes the division-by-zero crash.
