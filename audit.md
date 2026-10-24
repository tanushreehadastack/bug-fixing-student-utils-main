# Audit

| Check | Result | Notes |
|---|---|---|
| Tests were written from the specification, not from the buggy code | Pass | Expected values come from the Lecture 8 spec table |
| Tests failed before the fix (RED) | Pass | 4 failures + 1 error, see `red_output.txt` |
| Only `student_utils.py` was changed during the fix | Pass | `test_student_utils.py` is identical in both commits |
| All 9 tests pass after the fix (GREEN) | Pass | See `green_output.txt` |
| RED and FIX are separate commits | Pass | See commit history |
| Edge case not covered: empty list `[]` | Open | `calculate_average([])` still raises `ZeroDivisionError`; not in the spec, so left as-is and documented |
| Edge case not covered: marks above 100 or negative | Open | No validation in spec; documented only |
