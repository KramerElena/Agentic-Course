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

## Quick start

1. Install **uv** using the instructions for your operating system below.
2. Open a terminal in the project folder—the folder containing `pyproject.toml` and `uv.lock`.
3. Run `uv sync` to install the project’s Python version and packages.
4. Open a lab notebook, select the project’s `.venv` Python kernel, and run the cells from top to bottom.

## 1. Install uv

`uv` is a tool that sets up Python and installs the packages this course needs. You do not need to install Python packages one by one.

### Windows

1. Open **PowerShell** from the Start menu.
2. Copy and run:

   ```powershell
   powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1 | iex"
   ```

3. Close PowerShell, open it again, and check the installation:

   ```powershell
   uv --version
   ```

### Linux

1. Open a **Terminal**.
2. Copy and run:

   ```bash
   curl -LsSf https://astral.sh/uv/install.sh | sh
   ```

   If `curl` is not installed, use:

   ```bash
   wget -qO- https://astral.sh/uv/install.sh | sh
   ```

3. Close the Terminal, open it again, and check the installation:

   ```bash
   uv --version
   ```

If the terminal says that `uv` cannot be found, close and reopen it once more. For more installation options, see the [official uv installation guide](https://docs.astral.sh/uv/getting-started/installation/).

## 2. Set up this project

Open the project folder in your editor, then choose **Terminal → New Terminal**. Make sure the terminal is in the main project folder: it should contain both `pyproject.toml` and `uv.lock`.

You can check with:

- **Windows PowerShell:** `dir pyproject.toml, uv.lock`
- **Linux:** `ls pyproject.toml uv.lock`

Now install everything the project needs:

```bash
uv sync
```

The first setup may take a few minutes and requires an internet connection. `uv sync` reads the project setup files, creates a private `.venv` environment, installs a compatible Python version if needed, and installs the course packages. This project requires Python 3.12 or newer.

To confirm Python is ready, run:

```bash
uv run python --version
```

Run `uv sync` again whenever the project dependencies are updated.

## 3. Choose a lab

| Lab | Notebook | What you’ll do |
| --- | --- | --- |
| Lab 1 — Local | `labs/1_lab1/1_lab1.ipynb` | Run the predefined workflow with Ollama. |
| Lab 1 — Cloud | `labs/1_lab1/1_lab1-cloud.ipynb` | Run the workflow through OpenRouter. |
| Lab 2 | `labs/2_lab2/2_lab2.ipynb` | Compare model responses and rank them. |

Read the setup notes at the top of each notebook before running it. Depending on the lab, you may need Ollama running or an API key stored in the project-root `.env` file. Keep API keys private; do not paste them into notebooks or commit them to the project.

## 4. Run a lab in your editor

1. Open one of the notebook files listed above.
2. If prompted, choose a Python kernel. Select the environment named `.venv` (or similar) with Python 3.12 or newer.
3. Run the notebook from the beginning. Choose **Run All** in the notebook toolbar, or click the first cell and press **Shift+Enter** to run cells one at a time.

If `.venv` is not listed as a kernel, run `uv sync` from the project folder and reopen the notebook. In VS Code or Cursor, install the Python and Jupyter extensions if the notebook controls are missing.

## 5. Run a notebook from the terminal

From the project folder, `uv run` can execute every cell in a notebook. For example:

```bash
uv run python -m nbconvert --to notebook --execute labs/1_lab1/1_lab1.ipynb
```

To execute another lab, use its notebook path:

```bash
uv run python -m nbconvert --to notebook --execute labs/1_lab1/1_lab1-cloud.ipynb
uv run python -m nbconvert --to notebook --execute labs/2_lab2/2_lab2.ipynb
```

This command runs cells in order and writes a separate executed notebook ending in `.nbconvert.ipynb`; the original notebook is left unchanged. Complete the notebook’s setup steps first. Some cells contact a model server or a cloud API, so they may take time or use API credits.

## If something goes wrong

- **`uv` is not recognized:** Close and reopen the terminal after installing it.
- **The notebook cannot find a package or kernel:** Run `uv sync` from the folder containing `pyproject.toml`, then select `.venv` as the notebook kernel.
- **A cell reports `NameError`:** Run the notebook from the first cell so the imports and setup cells run before the later cells.
- **A model request fails:** Check that the notebook’s required model server is running and that its model/API key setup is complete.

---

Copyright © 2026 Dr Elena Kramer, Braude College, Israel. This notice applies to original text in this README only; third-party materials retain their respective rights.
