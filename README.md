# ADB project macroeconomic data

Annual data extracted from the IMF Public Finances in Modern History database, the Jordà-Schularick-Taylor Macrohistory Database, and the Long-Term Productivity Database. The CSVs are in tidy/long format: one row per country, year, and measure. They retain each source's definitions and units; they are not a harmonized panel.

## Files

| File | Coverage | Measures |
|---|---|---|
| [`data/imf_public_finances.csv`](data/imf_public_finances.csv) | 151 country codes, 1800–2024 | Public debt, revenue, expenditure, primary expenditure, interest paid, primary balance, real GDP growth, real long-term government bond yield, and two derived deficit measures |
| [`data/macrohistory_jst.csv`](data/macrohistory_jst.csv) | 18 countries, 1870–2020 | Public debt/GDP, long-term interest rate, unemployment rate, CPI, CPI-derived inflation, and two real GDP-per-capita series |
| [`data/long_term_productivity.csv`](data/long_term_productivity.csv) | 24 source country codes, 1890–2024 | GDP per capita, labor productivity, labor input per capita, and total factor productivity |

Observations with missing source values are omitted. Country codes and coverage follow the source files; `ZE` in the productivity file is the source's Euro-area aggregate. Values and definitions should not be compared across sources without checking their documentation.

## Definitions and transformations

- **IMF deficits:** `overall_deficit` is expenditure minus revenue; `primary_deficit` is the negative of the reported primary balance. Positive values therefore indicate a deficit. Both are derived from IMF series in percentage-of-GDP units.
- **JST inflation:** `inflation_yoy` is calculated from the source CPI as `(CPI[t] / CPI[t-1] - 1) * 100`, only where both adjacent years are observed.
- **Employment:** These extracts do not contain a directly comparable employment level or employment rate. JST's unemployment rate and the productivity source's labor-input-per-capita series are included as related, but distinct, labor-market measures.
- Other values are preserved as reported. In particular, the productivity workbook's measures have not been rescaled or rebased here.

## Sources, citations, and use

- **IMF Public Finances in Modern History** — [database and downloads](https://www.imf.org/external/datamapper/datasets/FPP). The current extract uses the December 2025 database series exposed by the IMF DataMapper API. The database describes coverage of 151 countries over 1800–2024. Cite the IMF database and the associated Mauro, Romeu, Binder, and Zaman work, “A Modern History of Fiscal Prudence and Profligacy.”
- **Jordà-Schularick-Taylor Macrohistory Database, release R6** — [database and terms](https://www.macrohistory.net/database/). Cite Jordà, Schularick, and Taylor (2017). The database is licensed under [CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/); this extract includes CPI-derived inflation and should be shared under the same terms.
- **Long-Term Productivity Database, v2.7 (February 2026)** — [database](https://www.longtermproductivity.com/) and [download/citation information](https://www.longtermproductivity.com/download.html). Cite Bergeaud, Cette, and Lecat (2016), “Productivity Trends in Advanced Countries between 1890 and 2012,” *Review of Income and Wealth*, 62(3), 420–444. The source states the data are free for non-commercial use and requests citation; consult its site for current terms.
- **Global Macro Database (GMD)** — [official data access](https://www.globalmacrodata.com/data.html), [variables](https://www.globalmacrodata.com/variables.html), and [research-use terms](https://www.globalmacrodata.com/license.html). GMD data are freely accessible for specified academic and non-commercial uses, but its terms prohibit re-hosting or redistributing the data, including partial or derived data, without permission. Accordingly, no GMD observations are copied into this repository. Obtain the current release directly from GMD and cite Müller, Xu, Lehbib, and Chen (2025).

Extracted 2026-10-05. Check the linked source pages for updates, revised observations, full variable definitions, and applicable terms of use.

## Related research

Download the reference spreadsheet: [`paper_references.xlsx`](related%20research/paper_references.xlsx).

- Croce, Mariano M., Thien T. Nguyen, Steve Raymond, and Lukas Schmid (2019). “[Government debt and the returns to innovation](https://doi.org/10.1016/j.jfineco.2018.11.010).” *Journal of Financial Economics*, 132(3), 205–225. [Bocconi repository record](https://iris.unibocconi.it/handle/11565/4012542) (the listed post-print is restricted access). The paper studies how government debt relates to the cost of capital for innovation-intensive firms and subsequent productivity and growth.
- Brancati, Emanuele, and Marco Macchiavelli (2019). “[The information sensitivity of debt in good and bad times](https://doi.org/10.1016/j.jfineco.2019.01.002).” *Journal of Financial Economics*, 133(1), 99–112. [Sapienza repository record](http://hdl.handle.net/11573/1351620). The publisher version is not open access; no authorized public PDF was identified.
