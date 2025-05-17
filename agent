# .agent   ― Place this file in the top-level directory of the repo
# Purpose:   Orient ChatGPT-Codex and suppress any package-install attempts
# -----------------------------------------------------------------------------

entrypoint: src/analysis.py        # ← change if your main script/notebook lives elsewhere

python_version: "3.10"             # Matches the Codex sandbox

dependencies: []                   # Empty list ⇒ Codex should NOT install anything

environment:
  internet_access: false           # Sandbox is offline; reinforces the no-install rule
  preinstalled_packages:           # (Informational only)
    - pandas
    - numpy
    - scipy
    - matplotlib
    - scikit-learn
    - statsmodels
    - plotly
    - networkx
    - pytables

run_command: "python src/analysis.py"  # What Codex should execute first

notes: |
  • All required libraries are already in the base image.  
  • Remove or comment-out any `pip install …` lines in your code; they will fail.  
  • Use relative paths (e.g., `data/…`) and save outputs to `/mnt/data/`.  
  • If you truly need a pure-Python dependency not on the list, bundle the wheel or
    module inside a `vendor/` folder and add `sys.path.append('vendor')` before import.
