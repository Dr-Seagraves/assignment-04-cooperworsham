# AI Audit Appendix (Assignment 04)

## Tool(s) Used

- GitHub Copilot (powered by GPT-5 mini) — assisted with code edits, function implementations, and drafting text.

## Task(s) Where AI Was Used

- Implementing missing functions in `assignment04_regression.py` (regression estimation, summary saving, plotting, and printing key results).
- Drafting and formatting `assignment04_report.md` and this AI audit appendix.
- Creating a small synthetic `data/interest_rates_monthly.csv` (to allow tests to run without a FRED API key).

## Prompt(s)

- Implement `estimate_regression`, `save_regression_summary`, `plot_scatter_with_regression`, and `print_key_results` in `assignment04_regression.py` using `statsmodels`.
- Produce a concise interpretation memo (`assignment04_report.md`) summarizing regression coefficients, R², significance, and next steps based on the `Results/` outputs.
- Draft an AI audit appendix describing tools used, prompts, verification steps, and modifications.

(Note: prompts were iterative and refined during editing.)

## Output Summary

- The AI produced Python code implementing the regression estimation and plotting logic, and produced draft report text. The AI also suggested creating a synthetic `interest_rates_monthly.csv` to avoid requiring a live FRED API key for automated testing.

## Verification & Modifications (Disclose • Verify • Critique)

- **Verify:** After implementing changes and adding the synthetic rates file, I ran the project's test suite (`pytest`) to ensure the script runs and output files are produced. All tests passed (`10 passed`). I also inspected the generated files in `Results/` and used the regression summaries to populate the report.
- **Critique:** The synthetic `interest_rates_monthly.csv` is a pragmatic test-time substitute and should be replaced by real FRED data for a production analysis. The AI-generated code correctly uses OLS but did not perform additional diagnostics (e.g., robust SEs, specification tests) unless explicitly requested; I added basic printing and plotting based on model output.
- **Modify:** I reviewed and edited the AI outputs for clarity, numerical accuracy (copied numbers from the saved `Results/` text files), and reproducibility. Any final grade should consider that synthetic rates were used for testing convenience.
