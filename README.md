This project is a reproducible data analytics pipeline and interactive query application designed to clean, process, and analyze the Metro Interstate Traffic Volume dataset. It handles data cleaning anomalies, feature engineering, trend visualizations, and historical pattern extraction.


- `part1_data_analytics/`: Contains documentation and PDF report summaries for traffic statistics and correlation coefficients.
- `part2_python/`: Contains the core data execution pipeline.
  - `pipeline.py`: Main processing script containing loading, schema checking, cleaning, and feature calculations.
  - `pipeline.log`: Automatically written tracking file recording execution milestones.
  - `figures/`: Automated chart graphics (`hourly_traffic_demand.png`, `weekday_vs_weekend_traffic.png`, `temperature_vs_traffic.png`).
  - `mini_app/`: Interactive Power BI dashboard sheets and analytical user layouts.
- `part3_machine_learning/`: Designated zone for future data training models and model weights.

- **Programming Language:** Python 3 (run through Anaconda Environment / Jupyter Notebook)
- **Data Libraries:** Pandas, NumPy
- **Plotting Library:** Matplotlib
- **Database System:** SQL / SQLite Studio
- **Business Intelligence:** Power BI Desktop

1. Ensure `pipeline.py` and `Metro_Interstate_Traffic_Volume.csv` are saved in the same local directory folder.
2. Open your Terminal or Anaconda Prompt window.
3. Change directories to your local path and run the pipeline engine script using:
   ```bash
   python pipeline.py
   ```
4. Check your folder workspace to see the generated `pipeline.log` tracking logs and the `.png` plot drawings.

1. When you run `python pipeline.py`, the terminal will automatically trigger the interactive command-line interface menu.
2. Type inputs `1`, `2`, or `3` into the text prompt lines to dynamically query date-specific records, pull up high-volume peak lists, or print side-by-side weekday summary counts.
3. Type option `4` to exit the active command loop cleanly.

This pipeline utilizes dedicated named instances (`logging.getLogger(__name__)`) to avoid global root capture conflicts.
- **Log Location:** All events are simultaneously echoed to the screen console and saved permanently inside **`part2_python/pipeline.log`**.
- **Message Format:** `Timestamp - Log Level - [Module Name] - Message`
- **Logging Level Meanings:**
  - `DEBUG`: Tracks fine-grained conversion ranges (such as Min-Max scaling boundaries).
  - `INFO`: Records expected operational milestones (data load sizes, visual asset saves, successful application exits).
  - `WARNING`: Highlights recoverable modifications (duplicate row counts, monthly median outlier replacements).
  - `ERROR`: Flags critical execution system barriers or malformed text argument user inputs.

All transformations are fully deterministic. By passing the uncleaned `Metro_Interstate_Traffic_Volume.csv` source file through `pipeline.py`, the cleaning algorithm will repeatedly isolate weather spikes using the exact monthly median mask logic, reconstruct uniform lowercase string labels, and plot identical target figures without drift.
