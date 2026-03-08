# KNN Live Coding Setup

This project is designed to run in a local virtual environment named `.venv`.

## macOS/Linux (bash or zsh)

```bash
cd /Users/nino/ML
python3 -m venv .venv
source .venv/bin/activate
python -m pip install --upgrade pip
python -m pip install -r requirements.txt
python -m ipykernel install --user --name knn-live --display-name "knn-live"
```

## Windows (PowerShell)

```powershell
cd C:\path\to\ML
py -m venv .venv
.\.venv\Scripts\Activate.ps1
python -m pip install --upgrade pip
python -m pip install -r requirements.txt
python -m ipykernel install --user --name knn-live --display-name "knn-live"
```

If activation is blocked, run this once in PowerShell and retry:

```powershell
Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass
```

## VS Code

1. Open this project folder in VS Code.
2. Open Command Palette (`Ctrl+Shift+P` / `Cmd+Shift+P`).
3. Run `Python: Select Interpreter` and choose the `.venv` interpreter.
4. Open either notebook.
5. In the notebook toolbar, click `Select Kernel` and choose `knn-live`.

`.vscode/settings.json` is configured for macOS/Linux with:

- `${workspaceFolder}/.venv/bin/python`

For Windows, change `python.defaultInterpreterPath` to:

- `${workspaceFolder}\\.venv\\Scripts\\python.exe`

## Troubleshooting (Kernel/Interpreter Mismatch)

- Notebook imports fail but terminal install succeeded:
  - Run the environment-check cell and confirm `sys.executable` points to this project’s `.venv`.
- `knn-live` kernel not listed:
  - Activate `.venv`, run the `python -m ipykernel install --user --name knn-live --display-name "knn-live"` command again, then reload VS Code window.
- Wrong interpreter selected:
  - Re-run `Python: Select Interpreter` and pick `.venv`, then re-select notebook kernel `knn-live`.
