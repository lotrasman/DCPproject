# Data Centric Programming Assignment 2026

Name: Matej Palata

Student number: A00043164

- [Assignment Brief](https://github.com/skooter500/dcp26-assignment/blob/main/dataset_assignment.md)

# Questions

What I want my data to answer:

1. Do I get more deep sleep on nights after I work out, and does a longer workout make a difference?
2. How does alcohol (none / light / party) affect how long and how well I sleep?
3. Does more sleep (or more deep and REM sleep) mean a better mood and more energy the next day? (compares each day with the previous row's sleep)

# Data Dictionary

Data file: `data/my_data.csv`

One row per day, from the morning until the next morning. A row contains everything from that day (workout, alcohol, meals, mood, energy) followed by the sleep that night. If I go to bed after midnight, that sleep still belongs to the previous day's row.

| Column       | Type              | Units                | How it is measured                                                                                  |
| ------------ | ----------------- | -------------------- | --------------------------------------------------------------------------------------------------- |
| date         | date (YYYY-MM-DD) | -                    | The day the row describes. The sleep is the night that follows it                                   |
| bedtime      | time (HH:MM, 24h) | -                    | Time I went to bed with the lights off, read from my Apple Watch (Sleep app). Can be after midnight |
| wake_time    | time (HH:MM, 24h) | -                    | Time I woke up the next morning, read from my Apple Watch (Sleep app)                               |
| sleep_mins   | numeric (integer) | minutes              | Total time asleep, as shown by my Apple Watch (Sleep app)                                           |
| deep_mins    | numeric (integer) | minutes              | Deep sleep, as shown by my Apple Watch (Sleep app)                                                  |
| rem_mins     | numeric (integer) | minutes              | REM sleep, as shown by my Apple Watch (Sleep app)                                                   |
| workout_mins | numeric (integer) | minutes              | Total workout time that day, timed with my Apple Watch. 0 if no workout                             |
| alcohol      | categorical       | none / light / party | Alcohol that day/evening. none = 0 drinks, light = 1–2 drinks, party = 3+ drinks                    |
| meals        | numeric (integer) | count                | Number of proper meals eaten that day. Snacks do not count                                          |
| mood         | numeric (integer) | 1–5                  | My overall mood that day, rated in the evening (scale below)                                        |
| energy       | numeric (integer) | 1–5                  | My overall energy that day, rated in the evening (scale below)                                      |

Rating scales:

| Score | Mood      | Energy                           |
| ----- | --------- | -------------------------------- |
| 1     | Very bad  | Exhausted, struggled to function |
| 2     | Bad       | Tired most of the day            |
| 3     | Neutral   | Normal                           |
| 4     | Good      | Energetic most of the day        |
| 5     | Very good | Full of energy all day           |

Measurement rules:

- **Evening:** before bed, I record that day's workout, meals, mood and energy (and alcohol if I already know it).
- **Morning:** right after waking, I read last night's sleep values from the Sleep app on my Apple Watch / iPhone and type them by hand into the previous day's row, plus alcohol if I didn't record it the night before. I do not export data from the app.
- I commit the CSV to GitHub every day.
- If I miss a value (for example, I forgot to wear the tracker), I leave it empty and write why in the diary. I never fill it in later from memory.
- Time in bed and sleep efficiency are not recorded. They are calculated in code from bedtime, wake_time and sleep_mins.

# Description of the project

I track my sleep every night, along with things that might affect it (working out, alcohol, meals) and how I feel the next day (mood, energy). I want to find out what actually helps or hurts my sleep, and whether better sleep really makes my days better.

# Data collection

## Photos

[Photos of me collecting data go here.]

## Diary

| Date         | Note                                               |
| ------------ | -------------------------------------------------- |
| [YYYY-MM-DD] | [Anything that changed, went wrong or was unusual] |

## Reflection

[Was the data collection useful? Did it work? Problems, missing data, outliers. Note: deep and REM sleep are estimates from my Apple Watch, not a medical measurement.]

# Instructions for use

[How to install and run the program.]

# How it works:

[How the code works: loading, database, analysis, interface.]

# Findings

[What my data told me about each question.]

# List of files in the project

| Files            | Source        |
| ---------------- | ------------- |
| data/my_data.csv | Self recorded |
| main.py          | Self written  |

# References

- [Item 1]

# What I am most proud of in the assignment

[TODO]

# What I learned

[TODO]
