# Predictive ICU Capacity Planning: Short-Term Adult ICU Occupancy Forecasting and Resource-Pressure Visualization

## Executive Overview
This project builds a retrospective ICU occupancy forecasting prototype that predicts near-term adult ICU utilization from historical hospital reporting data. The output can be explored through an explanatory dashboard with forecast curves, evaluation scores, alert thresholds, and hypothetical capacity scenarios.

> **Note:** All outputs are retrospective/research-only until prospectively validated. This is a data-driven decision-support prototype and is NOT intended for clinical triage, staffing decisions, or real-time clinical status indication.

## Datasets
This project uses verified historical datasets published by the U.S. Department of Health and Human Services (HHS).
*   **Primary Source:** HHS corrected state timeseries (U.S. state / daily)
*   **Data Link:** [HHS State Timeseries Data](https://healthdata.gov/d/sgxm-t72h)
*   *Note: The historical source ends in May 2024.*

## Project Capabilities
*   **Predict:** Adult ICU occupancy rate (0-100%) for a specified horizon.
*   **Compare:** Naïve forecasting baselines with statistical and machine-learning methods.
*   **Explore:** Hypothetical staffing/capacity scenarios (does not automate bed allocation).
*   **Communicate:** Future utilization estimates, historical validation errors, and planning-threshold crossings.

## Executable Setup and Commands
To run this project locally, clone the repository and run the following commands in your terminal:

1. Create and activate a virtual environment:
bash
python -m venv .venv
source .venv/bin/activate  # On Windows use: .venv\Scripts\activate

2. Install dependencies:
bash
pip install -r requirements.txt

3. Run the synthetic smoke test:
bash
python make_demo_data.py
python train.py -csv demo_synthetic.csv -mode state -entity DEMO -horizon 7

4. Launch the dashboard:
bash
streamlit run app.py


## Limitations & Disclaimers
*   **Not a clinical deployment:** This model cannot guarantee future bed availability or provide life-saving triage advice.
*   **State-level limitation:** State-level aggregate data cannot support an individual hospital forecast. 
*   **Thresholds:** Any warning thresholds (e.g., >90%) are configurable planning examples, not validated clinical definitions of unsafe occupancy.