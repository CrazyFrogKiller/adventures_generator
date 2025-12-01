Quickstart — get running in ~5 minutes
=====================================

This project is a small "Quest Master" app: a generator/editor for fantasy quests
with lightweight gamification and document export features.

If you just want to try the app quickly (no GUI), run the included performance
script that generates test quests used during development.

Prerequisites
-------------

- Python 3.10+ (3.11 recommended)
- Optional: system packages for WeasyPrint if you plan to export PDFs. On many
  Linux distributions you need libpango, libcairo and friends.

Install (quick)
---------------

1. Create and activate a virtual environment:

```bash
python3 -m venv .venv
source .venv/bin/activate
```

2. Install runtime dependencies (fast path — installs core libs; very heavy
   packages for export may be skipped if you only want to run tests):

```bash
pip install -r requirements.txt
```

Run the performance script (boss fight)
--------------------------------------

This script creates 100 test quests and prints timing info. It's useful to
check that the app's core logic is working on your machine.

```bash
python3 tests/test_boss_fight.py
```

Run the GUI (if you installed PyQt6)
-----------------------------------

If you installed GUI dependencies (PyQt6), start the main app:

```bash
python3 main.py
```

Notes & tips
------------

- The project uses SQLite by default (`adventures.db`) — safe and simple for
  local development. Tests may use `:memory:` to avoid creating files.
- Exporting to PDF/DOCX requires additional libraries (WeasyPrint,
  python-docx). If you hit errors while exporting, install the missing
  packages and system dependencies and try again.
- If you want persistent gamification state, we can add storage to the
  `GamificationEngine` — tell me and I'll add it.
