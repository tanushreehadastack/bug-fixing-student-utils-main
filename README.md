# Bug Fixing Using AI — `student_utils.py`

A small Python module with three bugs, found and fixed with the **RED → FIX → GREEN** testing cycle.

## What `student_utils.py` contains
| Function | Purpose |
|---|---|
| `calculate_average(marks)` | Average of a list of marks |
| `is_passing(mark)` | `True` if the mark is at least the pass mark (40) |
| `get_grade(average)` | `Distinction` (≥90), `First` (≥60), `Second` (≥45), else `Fail` |

## How to run the tests
```bash
python test_student_utils.py
```

- **Number of tests:** 9
- **Final result:** all 9 tests passing (`OK`)

## RED → FIX → GREEN
| Stage | What was done | Proof |
|---|---|---|
| **RED** | Wrote 9 unit tests from the spec and ran them against the buggy code | `red_output.txt` — 4 failures, 1 error |
| **FIX** | Changed only the implementation, never the tests | Second commit diff of `student_utils.py` |
| **GREEN** | Re-ran the exact same tests | `green_output.txt` — 9 passed |

## Bugs found and fixed
1. **Wrong average** — divided by `len(marks) - 1` → now `len(marks)`.
2. **Pass boundary** — `>` excluded a mark of exactly 40 → now `>=`.
3. **Grade order** — Distinction check was unreachable → moved to the top.

Full details in [`bug_notes.md`](bug_notes.md). Review notes in [`audit.md`](audit.md).

## Files
- `student_utils.py` — the fixed module
- `test_student_utils.py` — the unchanged test suite
- `red_output.txt` / `green_output.txt` — test output before and after the fix
- `bug_notes.md`, `audit.md`
