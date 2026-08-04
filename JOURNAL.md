## Week 7 — Issue selection

**Issue link:** https://github.com/ascherj/pathreview/issues/156

**Issue title:** README scorer test fixture is too short for its own word-count assertion

**Tier:** [x] Tier 1  [ ] Tier 2  [ ] Tier 3

**Problem summary:**
The README scorer test uses a sample README that is shorter than the minimum
word count required by the test's own assertion. This causes the test to fail
because of the test data rather than because the scorer is behaving incorrectly.
The issue affects the README scorer unit tests. A successful fix will update the
fixture so it contains enough words while continuing to test the intended scorer
behavior.

**Selection notes — “Is this right for me?” checklist:**
I selected this issue because it is labeled Tier 1 and has a small, clearly
defined scope. The issue appears to involve updating an existing test fixture
rather than changing core application or database logic. I can identify the
relevant unit test, reproduce the failure, make a focused change, and run the
affected tests to confirm the fix. This makes the issue appropriate for my first
contribution to a larger codebase.

**Branch name:** test/156-readme-scorer-fixture

**Setup confirmation:** [x] App runs locally at localhost:5173

**Cohort ledger:** [x] Issue added to cohort ledger

## Week 8 — Reproduction & solution planning

**Reproduction commit link:** [https://github.com/DelightOti/pathreview/commit/b995ff04b624d17a9d116697a75e0bf796597894]

**Reproduction summary:**  
I activated the project’s virtual environment and ran `python -m pytest tests/unit/test_readme_scorer.py -q`. The test suite produced 1 failed test and 22 passing tests. The failing test expected the README fixture to contain more than 100 words, but the scorer counted only 51 words and categorized it as `minimal`.

**PLAN.md link:** (https://github.com/DelightOti/pathreview/blob/test/156-readme-scorer-fixture/PLAN.md)

**Blockers or open questions:**  
I still need to confirm whether the maintainers prefer expanding the README fixture to more than 500 words or changing the expected category. Based on the test name and existing category tests, expanding the fixture appears to match the intended behavior.

**Blockers:**
Before making my changes, I ran `make check`. It failed with 182 pre-existing lint errors across unrelated files. I will rerun it after my changes to confirm that I did not introduce any new failures.

## Week 9 — Solution building & PR submission

### Check-in 1 (mid-week)

**Current progress:**
I reproduced issue #156 and updated the README scorer test fixture so that it
contains enough realistic content to satisfy the intended word-count threshold.
I also updated the related unit test annotations and confirmed that the focused
README scorer tests pass.

**Next steps:**
Request peer or mentor feedback on the pull request, address any relevant
feedback, confirm that my changes introduce no new failures, and finalize the
submission.

**Blockers:**
The repository already had pre-existing lint errors and failing unit tests
unrelated to my issue. I documented the existing failures and compared the
results before and after my changes.

---

### Check-in 2 (end of week)

**PR link:** https://github.com/ascherj/pathreview/pull/610

**Branch:** `test/156-readme-scorer-fixture`

**What you built:**
I expanded the README fixture used by the comprehensive README scorer test so
that it contains enough meaningful content to meet the scorer’s word-count
expectation. This fixes the test data without changing the production README
scorer logic.

**Tests added or updated:**
Updated `tests/unit/test_readme_scorer.py`. The focused failing test now passes,
and the complete README scorer test file passes with 23 tests.

**Self-review confirmation:** [x] make check introduces no new failures  [x] make test-unit introduces no new failures

**Draft PR feedback received from:** none yet