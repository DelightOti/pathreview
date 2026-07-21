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