# README: The Goalkeeper Moneyball Project
This project utilizes Unsupervised Machine Learning (K-Means Clustering) to identify statistical archetypes of Goalkeepers in the English Premier League (1992–2021). The goal is to build a Risk Assessment Tool for recruitment, predicting the probability of a goalkeeper maintaining their performance level next season.
## How to Run This Code
Follow these steps to execute the notebook and explore the Goalkeeper Moneyball model:
### 1. Open the Notebook in Google Colab
Ensure you are running this notebook in a Google Colab environment.
### 2. Upload the Data File
This notebook requires a single Excel file named `Combined Soccer Data.xlsx`. 
*   **Upload Location:** In the Colab interface, click the folder icon on the left sidebar to open the 'Files' section. Then, click the 'Upload' icon (the page with an arrow pointing up) and select `Combined Soccer Data.xlsx` from your local machine.
*   **Important:** The file *must* be named `Combined Soccer Data.xlsx` for the first cell to load it correctly.
### 3. Execute Cells Sequentially
Run each code cell in the notebook from top to bottom. You can do this by clicking the 'play' button next to each cell or by selecting 'Runtime' -> 'Run all' from the Colab menu.
#### Breakdown of Key Sections:
*   **Cell 2: 1. Data Pipeline (ETL & Ingestion)**
    *   Loads `Combined Soccer Data.xlsx` and performs initial data cleaning and merging. 
    *   **Action:** Run this cell first after uploading the data.
*   **Cell 4: 2. Feature Engineering (Normalization)**
    *   Filters for goalkeepers, aggregates their match data by season, and calculates normalized performance metrics (e.g., saves per match, save percentage).
    *   **Action:** Run this cell.
*   **Cell 6: 3. Core Model (Unsupervised Learning)**
    *   Applies K-Means clustering to classify goalkeepers into 'Elite Shield', 'Busy Shot-Stopper', and 'Underperformer' archetypes.
    *   **Action:** Run this cell.
*   **Cell 8: 4. Visualization (The Performance Map)**
    *   Generates a scatter plot visualizing goalkeeper performance across the defined archetypes.
    *   **Action:** Run this cell.
*   **Cell 10: 5. Predictive Modeling (Transition Matrix)**
    *   Calculates and visualizes the probability of a goalkeeper transitioning between performance tiers from one season to the next.
    *   **Action:** Run this cell.
*   **Cell 12: 6. The Product Interface (Interactive Report)**
    *   This cell provides an interactive scouting report for a specified player.
    *   **Action:**
        1.  **OpenAI API Key:** To enable AI-generated scout notes, you need an OpenAI API key. Replace `"sk-proj-..."` with your actual API key, or store it in Colab Secrets and uncomment `openai_api_key = userdata.get('openai_api_key')`.
        2.  **Search Player:** Modify the `search_name` variable (e.g., `search_name = "De Gea"`) to view a report for a different goalkeeper.
        3.  Run this cell.
*   **Cell 14: 7. The Moneyball Matrix: Finding Undervalued Assets 💎**
    *   Identifies undervalued goalkeepers based on Goals Saved Above Average (GSAA) and club size.
    *   **Action:** Run this cell.
*   **Cell 16: 8. Advanced Scouting: The Radar Chart 🕸️**
    *   Generates a radar chart comparing a specific player's stats against the 'Elite Tier Average'.
    *   **Action:** You can modify the `plot_radar("Pickford", "2019/20")` line to analyze different players and seasons. Then, run this cell.
*   **Cell 18: 9. Calculate & Visualize GSAA (Value Added) 📈**
    *   Calculates and visualizes the Goals Saved Above Average (GSAA) metric for all goalkeeper seasons.
    *   **Action:** Run this cell.
### Troubleshooting
*   **`FileNotFoundError: 'Combined Soccer Data.xlsx' not found`**: Ensure the `Combined Soccer Data.xlsx` file has been uploaded to the Colab environment and is correctly named.
*   **Missing DataFrames (e.g., `gk_season_stats` not defined)**: Ensure all preceding cells have been run successfully. The notebook is designed to be executed sequentially.
### Enjoy exploring the Goalkeeper Moneyball insights!
