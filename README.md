<p align="center">
  <img src="assets/01_course_overview.png" alt="An overview of the AI agents course" width="170">
</p>

<h1 align="center">Agents Course</h1>
<p align="center"><strong>Copyright © 2026 Dr Elena Kramer, Braude College, Israel</strong></p>
<p align="center">A hands-on introduction to LLMs, workflows, and AI agents.</p>

<p align="center">
  <img src="assets/02_llm.png" alt="Large language models" width="110">
  <img src="assets/03_workflow.png" alt="A predefined workflow" width="110">
  <img src="assets/04_agentic_ai.png" alt="AI agents" width="110">
</p>

Welcome! This repository contains interactive Python notebooks for learning how to build with language models and AI agents. Follow the steps below to set up the project and run your first lab.

## Quick start (Windows)

1. Install **Visual Studio Code**, **Git**, and the **Python** and **Jupyter** VS Code extensions.
2. Install **uv** in **PowerShell**.
3. Clone this repository from GitHub using Git.
4. In the project folder, run `uv sync` in PowerShell.
5. Open a notebook in VS Code, select the project's `.venv` Python kernel, and run the cells.

## 1. Install Visual Studio Code

Download and install [Visual Studio Code](https://code.visualstudio.com/).

## 2. Install Git

Download and install [Git for Windows](https://git-scm.com/downloads/win). Git is a tool for downloading the course project and getting updates from GitHub.

Open **PowerShell** (search for it in the Windows Start menu) and run:

```powershell
git --version
```

If Git is not recognized, close and reopen PowerShell after installation.

## 3. Install Python and Jupyter extensions in VS Code

Open VS Code and select **Extensions** on the left (or press `Ctrl+Shift+X`). Install both Microsoft extensions:

- [Python](https://marketplace.visualstudio.com/items?itemName=ms-python.python) — Python editing, running, debugging, and environment selection.
- [Jupyter](https://marketplace.visualstudio.com/items?itemName=ms-toolsai.jupyter) — Open and run `.ipynb` notebooks cell by cell.

**You do not normally need to install Python separately.** The `uv` tool will install the Python version needed by this project if it is missing.

## 4. Install uv

`uv` is a tool that sets up Python and installs the packages this course needs. You do not need to install Python packages one by one.

### Windows (PowerShell)

Open **PowerShell** and run:

```powershell
irm https://astral.sh/uv/install.ps1 | iex
```

Close PowerShell, open it again, and check:

```powershell
uv --version
```

### Linux (Terminal)

Open a terminal and run:

```bash
curl -LsSf https://astral.sh/uv/install.sh | sh
```

If `curl` is not installed, use:

```bash
wget -qO- https://astral.sh/uv/install.sh | sh
```

Close and reopen the terminal, then run `uv --version`.

For other installation options, see the [official uv installation guide](https://docs.astral.sh/uv/getting-started/installation/).

## 5. Download the course project from GitHub

On Windows, open **PowerShell** and run:

```powershell
cd $HOME
git clone https://github.com/KramerElena/Agentic-Course.git
cd Agentic-Course
```

These commands download the project and move into its folder. To check the project files, run:

```powershell
dir pyproject.toml, uv.lock
```

On Linux, run `git clone https://github.com/KramerElena/Agentic-Course.git` and then `cd Agentic-Course` in a terminal.

## 6. Set up the project with uv sync

From the **project folder** (the folder containing `pyproject.toml` and `uv.lock`), run:

```powershell
uv sync
```

The first setup may take a few minutes and requires an internet connection. `uv sync` creates the `.venv` environment, installs a compatible Python version if needed, and installs the course packages. This project requires Python 3.12 or newer.

Check the Python version:

```powershell
uv run python --version
```

Run `uv sync` again whenever the project dependencies are updated. **`uv sync` does not install uv itself**; you installed uv in step 4.

## 7. Open the project in VS Code

In PowerShell, while you are inside the project folder, run:

```powershell
code .
```

If `code` is not recognized, open VS Code and choose **File → Open Folder**, then select the `Agentic-Course` folder.

Press `Ctrl+Shift+P`, choose **Python: Select Interpreter**, and select the Python interpreter in `.venv` (on Windows, `.venv\Scripts\python.exe`).

## 8. Choose a lab

| Lab | Notebook | What you'll do |
| --- | --- | --- |
| Lab 1 — Local | `labs/1_lab1/1_lab1.ipynb` | Run the predefined workflow with Ollama. |
| Lab 1 — Cloud | `labs/1_lab1/1_lab1-cloud.ipynb` | Run the workflow through OpenRouter. |
| Lab 2 | `labs/2_lab2/2_lab2.ipynb` | Compare model responses and rank them. |

Read the setup notes at the top of each notebook before running it. Depending on the lab, you may need Ollama running or an API key stored in the project-root `.env` file. Keep API keys private; do not paste them into notebooks or commit them to the project.

## 9. Run a lab in VS Code

1. Open a `.ipynb` file from the table above.
2. Click **Select Kernel** and choose the Python environment inside `.venv`.
3. Click **Run All**, or run one cell at a time with **Shift+Enter**.

If `.venv` is not listed, run `uv sync` again and reopen the notebook. The project environment must contain `ipykernel` to run notebooks.

## 10. Run a notebook from the terminal (optional)

From the project folder, you can execute a notebook with `nbconvert` if it is included in the project's dependencies:

```powershell
uv run python -m nbconvert --to notebook --execute labs/1_lab1/1_lab1.ipynb
```

Other examples:

```powershell
uv run python -m nbconvert --to notebook --execute labs/1_lab1/1_lab1-cloud.ipynb
uv run python -m nbconvert --to notebook --execute labs/2_lab2/2_lab2.ipynb
```

This creates a separate executed notebook ending in `.nbconvert.ipynb`. Complete the notebook's setup steps first. Some cells contact a model server or cloud API and may use API credits.

## 11. Verify your setup

Open **Terminal → New Terminal** in VS Code and make sure it is **PowerShell** on Windows. Run:

```powershell
git --version
uv --version
uv run python --version
```

Then open a course notebook and run its first cell.

## If something goes wrong

- **`git` or `uv` is not recognized:** Close and reopen PowerShell after installation.
- **`code` is not recognized:** Open the folder through **File → Open Folder** in VS Code.
- **The notebook cannot find a package or kernel:** Run `uv sync` from the folder containing `pyproject.toml`, then select `.venv` as the notebook kernel. Ask the instructor if `ipykernel` is missing from project dependencies.
- **PowerShell blocks environment activation:** You do not need to activate `.venv` manually; use `uv run` and select the `.venv` interpreter in VS Code.
- **A cell reports `NameError`:** Run the notebook from the first cell.
- **A model request fails:** Check that the required model server is running and that its model/API key setup is complete.

---

Copyright © 2026 Dr Elena Kramer, Braude College, Israel. This notice applies to original text in this README only; third-party materials retain their respective rights.
