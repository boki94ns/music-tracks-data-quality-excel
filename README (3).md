# Music Tracks Dataset: Excel Data Quality & Exploration

**Data Analytics Portfolio Project | Microsoft Excel**

## 📥 Open the Excel Workbook

**[View or download the complete Excel file](songs%281%29.xlsx)**

The workbook includes the underlying song records, artist and year lookup sheets, and an initial completeness-check worksheet. On GitHub, use **Download raw file** to save the `.xlsx` file and open it in Microsoft Excel.

## Project Overview

This project focuses on exploring the structure and quality of a music dataset in Microsoft Excel. The file organizes song information alongside artist and year reference tables, and includes checks of populated cells and numeric data types.

**Project scope:** data inspection, organization, and initial validation. The uploaded workbook does **not** contain a completed dashboard, PivotTable report, or music-prediction model. Suggested future analyses appear separately below.

## Dataset at a Glance

| Measure | Value |
|---|---:|
| Song records | 1,941 |
| Distinct artists referenced | 835 |
| Artist lookup entries | 835 |
| Year lookup entries | 23 |
| Core fields in the `Songs` sheet | 18 |
| Distinct song titles | 1,879 |
| Distinct genre labels/combinations | 59 |
| Explicit tracks | 537 (27.7%) |
| Mean popularity score | 59.63 |
| Median song duration | 3.72 minutes |

*These descriptive figures were calculated from the submitted workbook for this portfolio overview; they are not presented as existing Excel dashboard outputs.*

## Workbook Structure

| Worksheet | Purpose |
|---|---|
| `Songs` | Main dataset containing song titles, artist/year identifiers, popularity and audio features |
| `Artists` | Maps `artist_id` to artist names |
| `Years` | Maps `year_id` to year values |
| `NULL_VALUES` | Uses `COUNTA` formulas to count populated cells in each of the 18 core song columns |

The `Songs` worksheet includes the following core fields:

- **Identification:** `artist_id`, `song`, `year_id`
- **Song metadata:** `duration_ms`, `explicit`, `popularity`, `genre`
- **Audio features:** `danceability`, `energy`, `key`, `loudness`, `mode`, `speechiness`, `acousticness`, `instrumentalness`, `liveness`, `valence`, `tempo`

The artist and year identifiers connect the main song list to reference sheets. This structure provides a foundation for later joins and grouped analysis.

## Excel Work Demonstrated

1. **Dataset organization:** song records are stored separately from artist and year lookup lists.
2. **Completeness inspection:** the `NULL_VALUES` sheet uses `COUNTA` across the main columns to report 1,941 populated cells per field.
3. **Data-type checks:** several `ISNUMBER` formulas appear in an additional area of the `Songs` sheet, allowing selected cells to be checked for numeric values.
4. **Initial data review:** track details and numerical audio attributes can be inspected and filtered for further analysis.

> **Important:** `COUNTA` counts non-empty cells; it does not directly count missing values. A result of 1,941 populated entries across 1,941 records suggests no blank cells in those 18 fields, but does not prove that every value is valid or consistently formatted.

## Data Quality Observations

A review of the supplied workbook highlighted two items that would benefit from validation before any downstream statistical analysis:

- **Year lookup:** `year_id = 23` maps to `202` in the `Years` worksheet. This is not a valid four-digit year and affects three records. Its intended value should be confirmed against the original data source.
- **Numeric formatting:** four `instrumentalness` values use comma decimal separators and are stored as text instead of numeric values. These would need consistent conversion before mathematical analysis.

Song titles can also repeat, so duplicate *titles alone* should not be considered duplicate records without reviewing other identifiers.

## Possible Next Analyses

*These are future portfolio enhancements, not completed analyses in the submitted workbook.*

- Compare average popularity across years and genres.
- Summarize the most represented artists and genre combinations.
- Examine distributions of song duration, danceability, energy, and valence.
- Explore relationships between audio features and popularity using scatter plots and correlation analysis.
- Build PivotTables, charts, and a compact Excel dashboard after resolving data quality issues.

## Tools and Skills

`Microsoft Excel` · `Data Inspection` · `COUNTA` · `ISNUMBER` · `Data Validation` · `Lookup Tables` · `Data Quality Review` · `Descriptive Statistics`

## Project Files

- **[`songs(1).xlsx`](songs%281%29.xlsx)** — original Excel workbook containing the dataset and existing validation worksheets.
- **`README.md`** — project documentation and data quality observations.

---

*Prepared as part of an evolving Data Analytics / Data Science learning portfolio. The workbook and analysis notes represent an educational project, not a production music recommendation system.*
