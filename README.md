# sauna-stats

Occupancy statistics for the **Sauna Lorrainebad** in Bern, regenerated every
night. The app [Lorakel](https://github.com/janlijanli/is_it_saunatime) reads
these files so it does not have to be rebuilt for every new day of data.

## Files

| File | What it holds |
| --- | --- |
| [`v1/model.json`](v1/model.json) | Forecast coefficients per horizon (15 min … 4 h), the typical curve per weekday, opening hours and announced exceptions |
| [`v1/stats.json`](v1/stats.json) | Statistics over all past sauna days: per weekday, records, context factors, the last 120 days and the last 14 in detail |
| [`v1/days.json`](v1/days.json) | Every past sauna day with its occupancy curve and that day's weather and Aare temperature |

Fetch them raw, for example:

```
https://raw.githubusercontent.com/janlijanli/sauna-stats/main/v1/stats.json
```

## Where the numbers come from

* **Occupancy** – the counter of the Sauna Lorrainebad, tapped by hand by the
  sauna team. Expect drift: the count is a good guide, not an exact headcount.
* **Weather** – [Open-Meteo](https://open-meteo.com), grid point Bern.
* **Aare temperature and flow** – the Swiss Federal Office for the Environment
  (BAFU) measuring station in Bern, via [Aareguru / existenz.ch](https://aareguru.existenz.ch).
* **School holidays** – [OpenHolidays API](https://openholidaysapi.org), canton of Bern.

This is a hobby project and is not affiliated with the Verein Sauna Lorrainebad.
