Markov-Switching Model for Inflation Analysis
This repository contains a Python script that simulates inflation data with two regimes (low and high inflation), fits a Markov-Switching Regression model using statsmodels, and visualizes the results. The script demonstrates regime-switching behavior in time series data, estimates transition probabilities, and evaluates model accuracy against simulated true regimes.
Overview
The script performs the following steps:

Data Simulation: Generates synthetic monthly inflation data from 2005 onwards, incorporating two Markov regimes:
Low inflation regime: Mean = 2%, Persistence = 0.7, Variance = 0.5
High inflation regime: Mean = 8%, Persistence = 0.9, Variance = 1.0
A deterministic trend and noise are added for realism.

Model Estimation: Uses statsmodels.tsa.regime_switching.MarkovRegression to fit a 2-regime model with switching variance and a constant trend plus exogenous time trend.
Visualization: Creates a 2x2 plot grid showing:
(a) Simulated inflation with true regimes highlighted.
(b) Inflation with estimated regimes highlighted.
(c) Smoothed probability of the high inflation regime.
(d) Boxplot of inflation distribution by estimated regime.

Numerical Results: Prints descriptive statistics, regime distribution, model accuracy, transition matrix, and expected regime durations.

Requirements

Python 3.x
Libraries:
numpy
pandas
matplotlib
statsmodels


Install dependencies using:
textpip install numpy pandas matplotlib statsmodels
Usage

Clone the repository:textgit clone https://github.com/your-username/markov-switching-inflation.git
cd markov-switching-inflation
Run the script:textpython markov_switching_model.py

The script will:

Generate and display the plots in a matplotlib window.
Print results to the console.

No command-line arguments are required. The random seed is set to 42 for reproducibility.
Output
Plots
A figure titled "Markov-Switching Model for Inflation - Complete Analysis" with four subplots as described above.
Console Output
Example output:
text======================================================================
MARKOV-SWITCHING MODEL RESULTS FOR INFLATION
======================================================================

Descriptive Statistics:
  Mean inflation: X.XX%
  Standard deviation: X.XX%
  Minimum: X.XX%
  Maximum: X.XX%

Estimated Regime Distribution:
  Low inflation periods: XXX (XX.X%)
  High inflation periods: XXX (XX.X%)

Model accuracy: XX.XX%

Estimated Transition Matrix:
  P(0→0): X.XXXX  |  P(0→1): X.XXXX
  P(1→0): X.XXXX  |  P(1→1): X.XXXX

Expected Duration of Regimes:
  Low inflation regime: XX.XX periods
  High inflation regime: XX.XX periods
Note: Actual values depend on the simulation and estimation.
Methodology Notes

Regime Simulation: Uses a simple Markov chain for regime transitions with probabilities P(0→0)=0.95 and P(1→1)=0.90.
Model Fitting: Includes a constant trend (trend='c') and an exogenous time trend variable. Variance switches between regimes.
Accuracy Calculation: Compares estimated regimes (based on smoothed probabilities >0.5) to true simulated regimes.
Transition Matrix: Extracted and adjusted for dimensionality; expected durations calculated as 1 / (1 - p_ii).

This script is for educational purposes to illustrate regime-switching models in econometrics.
License
MIT License. See LICENSE for details.
Contributing
Feel free to open issues or submit pull requests for improvements, such as adding real data integration or more regimes.
