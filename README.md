# Formula_1
Analysis of Formula 1 data to establish a method of calculating how "competitive" a Formula 1 racing season was.

## Data Source
https://www.kaggle.com/datasets/rohanrao/formula-1-world-championship-1950-2020

(downloaded 26.04.2024)

This consists of (.csv files):
- circuits
- constructor_results
- constructor_standings
- constructors
- driver_standings
- drivers
- lap_times
- pit_stops
- qualifying
- races
- results
- seasons
- sprint_results
- status

## Factors to consider to determine "competitiveness"

## Rating algorithm

The intention is to apply the Elo rating method (from chess) to this analysis, applying the premise that each race is a series of 1v1 matchups between drivers evaluated over the field as a whole.

Method:
1. Initialise a start rating (tbc)
2. Define what is a "win" or "loss" between two drivers (absolute position vs peformance compared to expected performance)
3. Calculate the expected score based on ratings
4. Update the ratings after each race
4.1 In order to update the rating, need to decide on a K-factor
5. Consider whether additional factors need to be considered on a race by race basis (course difficulty, weather, temperature)
6. Validate and iterate

Formulae:

Expected Scores:
$E_A = \frac{1}{1+10(R_B - R_A) / 400}$

Update rating:
$R`_A = R_A + K \cdot (S_A - E_A)$