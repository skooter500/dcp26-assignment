# Data Centric Programming 2026 Assignment

## Hand-Made Data

Please note!! This assignment brief is subject to minor ammendments.

This assignment is Category 2 for use of AI:

![](images/Screenshot%20from%202025-11-03%2017-46-03.png)

**The data itself is Category 1 - NO AI.** Every value in your dataset must be measured, counted or observed by you.

**Weight:** 30%
**Submission:** GitHub repository URL + In-class demo

---

### The brief!

The internet is full of datasets that somebody else collected. This year you are going to make your own.

Pick something in your life that you can **measure or count every day**. Go out and record it - by hand - day after day, for the rest of the semester. Then build a Python application that stores your data in a database, analyses it with pandas, and lets a user explore it and find out something interesting.

At the end you will know your data better than anyone in the world, because you are the only person in the world who has it.

Your dataset should have:

- **At least 5 columns**
- **At least 50 rows**
- A **date** (and optionally a time) on every row
- At least **one numeric** column you measured or counted (a number you can average, plot, sum)
- At least **one categorical** column (a label you can group by - e.g. weather, day type, location, mood)

You can record more than one row per day (e.g. one row for every bus you catch, every coffee you buy), but you **must record something every day**. Start today. Every day you wait is a row you will not get back!

---

### What counts as hand-made data?

The whole point of this assignment is **human effort**. The marks for data collection reward the time, care and consistency you put into gathering your data, not how big or fancy it is. Fifty rows that you lovingly recorded at the same time every morning beat ten thousand rows downloaded from Kaggle.

**Allowed:**

- Counting things with your own eyes (birds at the feeder, red cars passing in 10 minutes, people on the 46A)
- Measuring things with instruments: a ruler, kitchen scales, a thermometer, a stopwatch, the step counter on your phone - **as long as you read the value and write it down yourself, each day**
- Rating things yourself on a scale you define (mood, energy, how good the coffee was)
- Recording things that happen to you (what time the bus arrived, how much lunch cost)

**Not allowed:**

- Downloading, scraping or using an API to get data
- Bulk exporting history from an app (Fitbit, Spotify, Strava, screen-time etc.)
- Making up, back-filling or "estimating later" data you didn't actually record on the day
- Any AI generated or synthetic data
- Recording personal data about other people without their consent. Count the cars, not the number plates!

If you are not sure if your idea is ok, ask me before you start.

---

### Some ideas to get you started

| Idea | Possible columns |
|---|---|
| My commute | date, bus route, scheduled time, actual time, minutes late, weather, seat (y/n) |
| Bird feeder watch | date, time, duration (mins), species, count, temperature, weather |
| Music practice | date, instrument, minutes practiced, tunes played, new tune learned (y/n), how it sounded (1-5) |
| Coffee log | date, time, where, drink, price, size, rating (1-5) |
| Sleep & mood | date, bedtime, wake time, hours slept, caffeine after 4pm (y/n), mood (1-5), energy (1-5) |
| Plant growth | date, plant, height (mm), leaves, watered (y/n), sunlight (hours), temperature |
| Traffic counter | date, time, location, cars, bikes, pedestrians, buses, weather |
| Spending | date, category, item, amount, shop, need vs want |
| Weather station | date, time, temperature, cloud cover, wind (Beaufort), rain (y/n), what I wore |

Make it about something you are curious about. You will spend a lot of time with this data, so choose something you actually care about!

Before you start, write down **two or three questions you want your data to answer**. For example: *"Is the 46A later when it rains?"* *"Do I sleep better on days I don't drink coffee after 4pm?"* *"Do more birds come to the feeder when it's cold?"* Pick columns that will help you answer those questions.

---

## Part 1: Data Collection (25%)

- Design your columns and write a **data dictionary** - a table in your README that lists every column, its type, its units and how you measure it. Decide on these rules before you start and stick to them.
- Record your data in a CSV file in your GitHub repo e.g. `data/my_data.csv`
- **Commit your CSV to GitHub every day you record data.** Your commit history is your evidence of daily human effort. A dataset that appears all at once in one commit the night before the deadline will be treated as not hand-made.
- Keep a short **collection diary** - a line or two whenever something interesting happens (forgot to record, changed method, weird outlier, instrument broke). Real data is messy and that's fine - just document it honestly. Missing days are better than invented days.
- Take a few **photos** of yourself collecting data (your notebook, the feeder, the thermometer, the bus stop). Put them in your README.

Example CSV:

```
date,time,route,scheduled,actual,minutes_late,weather,got_seat
2026-10-19,08:05,46A,08:02,08:09,7,rain,n
2026-10-20,08:03,46A,08:02,08:03,1,sunny,y
2026-10-21,08:11,145,08:05,08:11,6,cloudy,n
```

## Part 2: Database & Loading (15%)

- Write Python code to read your CSV and insert the rows into a table in SQLITE or MYSQL
- Clean and validate your data as you load it: check types, handle missing values, flag values that are out of range
- Write some SQL queries that answer simple questions about your data (`GROUP BY`, `ORDER BY`, `WHERE`, `AVG`, `COUNT`)

## Part 3: Analysis & Visualisation (25%)

Load your table into a pandas DataFrame:

```python
df = pd.read_sql("SELECT * FROM my_table", conn)
```

Write functions to analyse the data. Use your imagination - what would someone want to know?


- Use matplotlib to make charts: values over time, comparisons between categories, distributions, relationships between two columns
- **Go back to your questions.** What did your data say? Were you surprised? Write up your findings in the README.

## Part 4: Interactive Elements (15%)

Create a way for a user to explore your data and run queries. This can be purely menu based like this:

- https://www.youtube.com/watch?v=p3Vui6q_wPw

Or you can use py5, tkinter, streamlit or django. Bonus points if the user can **add today's row** through your interface!

## Part 5: Demo, Documentation & GitHub (20%)

Your README must be in [this format](README.MD) and must also include:

- Your data dictionary
- Your collection diary
- Photos of you collecting data
- Your questions and what your data told you

And:

- Use docstrings for all functions and classes
- Include type hints where appropriate
- Add comments for complex logic
- Make regular commits!!

---

## Rubric

Your grade is made up of five parts. Read each row and ask yourself "which box does my project fit in?". You do not need to hit every single thing in a category to get that grade. The A column is an outstanding project, *not a checklist*!

| | A | B | C | D | E |
|---|---|---|---|---|---|
| **Data collection & human effort (25%)** | A rich, original dataset that could only have come from you. Well over 5 columns and 50 rows, recorded every day across the whole semester, visible in a daily commit history. Clear, consistent measurement rules in a detailed data dictionary. Honest collection diary that discusses problems, missing data and outliers. Photos of collection in progress. Interesting questions set out at the start. | 5+ columns, 50+ rows recorded regularly with a steady commit history. Good data dictionary and diary. A clear question or two. A few gaps, explained. | Meets the 5 column / 50 row minimum. Recorded over several weeks, with some gaps or bursts of commits. Basic data dictionary. Little or no diary. | Small dataset, well under the minimums, or recorded in a few sittings. Not clear how it was measured. | No data, or data that was downloaded, exported, made up or AI generated. |
| **Database & loading (15%)** | CSV loaded into a well designed table with sensible column types. Data validated and cleaned on load, with missing and out of range values handled. Several useful SQL queries using grouping, ordering and aggregate functions. | Data loads into SQLITE or MYSQL with sensible types. Some cleaning. A few SQL queries. | Data loads into a database table. Basic `SELECT` queries. Little or no cleaning. | Loading partly works or needs manual fixing. | No database, or code does not run. |
| **Analysis & visualisation (25%)** | Many well chosen pandas functions: filtering, grouping, date and day-of-week analysis, comparisons between columns. Clear, labelled, well chosen charts. Your questions are answered with evidence, and you discuss what surprised you and the limits of your data. | Several useful pandas functions and a few clear charts. Findings written up with some discussion. | A few basic pandas functions (filter, mean, count). One or two charts. Brief findings. | Minimal analysis. Mostly printing the DataFrame. No charts. | No analysis. |
| **Interactive elements (15%)** | Polished, easy to use interface. A user can filter, query, see charts and add new rows. Handles bad input gracefully. | Working menu or GUI that runs several queries and shows results clearly. | Simple menu with a few options. Some rough edges. | Interface barely works or crashes on bad input. | No interface. |
| **Demo, documentation & GitHub (20%)** | Confident live demo: you talk about your data, how you collected it, what you found and how your code works. README has everything: data dictionary, diary, photos, screenshots, findings, what you wrote yourself, what you borrowed (with links) and a reflection. Clean, commented code with docstrings and type hints. Can explain any line of it. | Good demo and README with minor gaps. Code mostly tidy and documented. | Demo happens but is rushed. README is present but missing sections. | Demo very brief or the app fails during it. README is a few lines. | No demo, or no documentation. |

### What the grades mean

- **A** - Outstanding. Went well beyond the brief. You would be happy to put this on your portfolio as-is.
- **B** - Very good. Everything in the brief is done properly and the data tells an interesting story.
- **C** - Good. The brief is met. The data and the code are your own.
- **D** - Pass. Something was submitted and runs, but a lot of the brief is missing.
- **E** - Fail. Nothing submitted, it does not run, or the data is not hand-made.

### How to do well

- **Start recording today.** You cannot catch up on data collection at the end. 50 days from now is the start of December!
- **Make it a habit.** Record at the same time every day. Set a phone reminder. Keep a small notebook in your bag.
- **Commit every day.** It takes 10 seconds and it proves the effort is yours.
- **Be consistent.** Same instrument, same place, same rules. If you have to change something, write it in your diary.
- **Be honest.** Missing a day is fine. Making up a day is not.
- **Make it yours.** Original and simple beats downloaded and complex. Your effort and curiosity are what is being rewarded.
- **Ask for help.** If you are stuck, ask in class or in the lab. I am a highly paid senior lecturer at your disposal every week!

## Submission Requirements

1. Submit a short proposal on Brightspace: what you will record, your columns and your questions (pass or fail - ungraded). Do this in the first week so you can start collecting!
2. **GitHub Repository URL** via Brightspace
3. In class demo

Optional elements:

- Add a column from a second source you also record yourself and look for relationships
- Statistical tests or a simple trend line / prediction
- Edit/delete rows through your interface
- Export a report to PDF
- A short YouTube video about your project
