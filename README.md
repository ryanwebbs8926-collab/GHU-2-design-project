# My Project

Short description of what this project does.

## Setup (first time)

Requires Python 3.10+ and Git.

**macOS / Linux**
```bash
./scripts/setup.sh
source .venv/bin/activate
```

**Windows (PowerShell)**
```powershell
.\scripts\setup.ps1
.\.venv\Scripts\Activate.ps1
```

Or manually:
```bash
python -m venv .venv
# activate it (see above), then:
pip install -r requirements/dev.txt
```

VS Code will detect `.venv` automatically. If it doesn't, press `Ctrl/Cmd+Shift+P` > **Python: Select Interpreter** > choose `.venv`.

## Updating your environment after pulling

When someone adds a dependency, re-run:
```bash
pip install -r requirements/dev.txt
```

## Adding a dependency

1. `pip install <package>`
2. Add it (with a version pin, e.g. `requests==2.32.3`) to `requirements/base.txt` (needed to run) or `requirements/dev.txt` (tools only).
3. Commit the requirements change.

`pip freeze` can show the exact installed version: `pip freeze | grep <package>`.

## Layout

```
src/            application code
tests/          pytest tests
requirements/   base.txt (runtime), dev.txt (runtime + dev tools)
scripts/        setup scripts
.venv/          local virtual environment (NOT committed)
```

## Run

```bash
python -m src.main
pytest
```
