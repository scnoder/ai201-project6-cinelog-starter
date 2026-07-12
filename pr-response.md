# PR Response Doc — CineLog Watchlist Feature

## AI Usage
<!-- Fill in at the end — how you used AI tools during this project -->

## Comment 1 — Rename
**What I did:** I changed the function name from `save_to_watchlist()` to `add_to_watchlist()`.
**How I verified:** I searched every instance of `save_to_watchlist()` and then changed the name and checked again to make sure that there are no more occurences of that name.

## Comment 2 — Deduplication
**What I did:** Added a duplicate check in `add_to_watchlist()` that looks for an existing watchlist entry with the same `user_id` and `film_id`. If one exists, the service raises `AlreadyInWatchlistError`. I also updated the route to return a 409 Conflict response when that exception is raised.

**How I verified:** Ran the full test suite with `pytest tests/ -v` and confirmed all tests passed. I also verified the duplicate-check pattern matches the existing implementation in `add_to_collection()`.

## Comment 3 — Missing test
**What I did:** Created `tests/test_watchlist.py` and added a test for attempting to add a film that does not exist. I modeled the test after `test_add_to_collection_nonexistent_film_raises` so the watchlist tests follow the same fixture and assertion pattern as the existing collection tests.

**How I verified:** Ran `pytest tests/test_watchlist.py -v` and `pytest tests/ -v`. All tests passed.

## Comment 4 — Default visibility
**My position:**
**Reasoning:**
**Tradeoff acknowledged:**

## Comment 5 — Sort order
**My position:**
**Reasoning:**
**Engagement with reviewer's point:**

## Comment 6 — Rebase
**What conflicted:**
**How I resolved it:**
**How I verified no conflict remains:**

## PR Description
<!-- Written at the end — feature overview, design decisions, manual testing steps -->