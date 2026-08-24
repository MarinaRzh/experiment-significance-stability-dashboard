# experiment-significance-stability-dashboard
Interactive dashboard for exploring how significance changes during AB tests and estimating when experiment results become stable enough to stop the AB test

The project explores a practical experimentation question: 
> How much time does it take to get the significant result and should we wait for such a long period of time (~ month) or we achieve significance during the first 2 weeks?

## What it shows

- P-value trajectories by days from the start day of each AB test
- Actual duration of AB experiment
- Options of using treatment / without treatment
- Filters by product, metric and start date
- The first day when statistical significance remains consistent until the end of the experiment
- Analysis of % of potential mistakes for the shorter duration

## Why it matters

Product teams often want to shorten experiment duration but early statistical significance may disappear as more data arrives. This dashboard includes real data of 905 AB tests during the 2 years with their real durations and potential shorten duration based on p-val estimation

## Methodology

For each AB experiment and metric:

1. The dashboard stores the p-value observed on each experiment day
2. A final significance is calculated from the latest available observation
3. `stable_day` represents the first day from which the significance remains aligned with the final verdict through the end of the observed period
4. For selected checkpoints, the dashboard estimates the share of experiments whose verdict would differ from the final verdict

## Data privacy

The public version contains synthetic data only. The structure was inspired by the real data, while all experiment identifiers, names, dates, categories, and values have been anonymised

## How to run

Clone the repository and open `index.html` in a browser

