# Terrorism Hotspots

I recommend downloading the HTML file to view the interactive Databricks visualizations properly.

## 📥 Download Datasets

This data project has been used as an assignment during the **LGM Data Science Virtual Internship**.

---

## 📝 Assignment

Imagine you are a **security or defense analyst**. Your task is to analyze the data and draw conclusions about the **distribution** and **nature** of terrorist incidents recorded around the world. Your analysis should include **maps** that visualize the location of different incidents. You may consider answering the following questions:

- 📈 How has the number of terrorist activities changed over the years? Are there specific regions where this trend differs from global averages?
- 💀 Is there a correlation between the number of incidents and the number of casualties? Can you spot any irregularities or outliers?
- 🔫 What are the most common methods of attacks? Do they vary across regions or time periods?
- 🗺️ Plot the locations of attacks on a map to visualize their regional spread.

Feel free to explore the data further and extract **additional insights** beyond these suggested questions.

---

## 🧾 Data Description

The provided compressed file `globalterrorismdb_0718dist.tar.bz2` is an extract from the **Global Terrorism Database (GTD)** — an open-source database containing information on **terrorist attacks worldwide from 1970 through 2017**.

The GTD includes systematic data on both **domestic and international** terrorist incidents, with over **180,000 recorded attacks**. It is maintained by the **National Consortium for the Study of Terrorism and Responses to Terrorism (START)**, based at the **University of Maryland**.

> ⚠️ Since the number of variables and records is very large, you're encouraged to **select a subset of columns** or **focus on a specific timeframe** for your analysis.

---

## 📚 Selected Columns - Explanation

| Column               | Description                                                                 |
|----------------------|-----------------------------------------------------------------------------|
| `success`            | Whether the terrorist attack was successful                                |
| `suicide`            | 1 = "Yes" (suicide attack), 0 = "No" (non-suicide)                         |
| `attacktype1`        | General method of attack (numeric code)                                    |
| `attacktype1_txt`    | General method of attack (text label)                                      |
| `targtype1_txt`      | General type of target/victim                                               |
| `targsubtype1_txt`   | More specific category of the target                                        |
| `target1`            | The specific person, building, or installation targeted                     |
| `natlty1_txt`        | Nationality of the target                                                   |
| `gname`              | Name of the group that carried out the attack                              |
| `gsubname`           | Additional details about the group (e.g., factions or subgroups)            |
| `nperps`             | Number of terrorists involved in the incident                               |
| `weaptype1_txt`      | General type of weapon used                                                 |
| `weapsubtype1_txt`   | More specific weapon subtype                                                |
| `nkill`              | Total confirmed fatalities                                                  |
| `nkillus`            | Number of U.S. citizens killed in the incident                              |

---

## 🧪 Hint: How to Load the Data

The `.tar.bz2` file is a compressed CSV. You can load it into a Pandas DataFrame like this:

```python
import pandas as pd

df = pd.read_csv("globalterrorismdb_0718dist.tar.bz2", compression="bz2")
