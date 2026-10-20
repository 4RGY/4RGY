<div align="center">

<a href="https://git.io/typing-svg">
  <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=27&pause=1200&color=3776AB&center=true&vCenter=true&width=620&lines=Hi%2C+I%27m+Argy+Anggara.;I+turn+Indonesian+public+data+into+pipelines.;Python+%2B+SQL+%2B+CI+that+actually+runs." alt="Hi, I'm Argy Anggara. I turn Indonesian public data into pipelines." />
</a>

**Information Systems student. Data analyst in training, builder by habit.**
I take raw data from Indonesian public sources (BMKG, IDX, government portals), clean it, test it, and ship it as something usable: a report, a dashboard, a bot.

[Portfolio](https://angg4ra.my.id) &nbsp;·&nbsp; [Email](mailto:argyang77@gmail.com) &nbsp;·&nbsp; [Live projects](#live-right-now)

</div>

## Live right now

| Project | What it is | Stack |
| :--- | :--- | :--- |
| **[SudutMata](https://www.sudutmata.my.id)** | News reading app with reader-focused layout and a companion Telegram bot | Next.js, Supabase, Telegram Bot API |
| **[Pantau DBD](https://pantau-dbd-seven.vercel.app)** | Dengue case prediction for Jakarta from weather and health-office reports. LightGBM + GLM, walk-forward evaluation | Python, LightGBM, Astro |
| **[Kataloji CRM](https://kataloji-crm-gamma.vercel.app)** | CRM and POS for a coffee shop: orders, promo, receipts, owner dashboard | Next.js 16, shadcn, Recharts |
| **[Portfolio](https://angg4ra.my.id)** | Personal site, built as a static Astro site with GSAP motion | Astro, Tailwind v4, GSAP |

## Data projects

Three pipelines, all Python, all pulling live Indonesian data. Every number is recomputed on each run, nothing is hardcoded, and each repo has offline tests plus a GitHub Actions job that keeps the data fresh.

<h3><a href="https://github.com/4RGY/ihsg-idx-analytics">ihsg-idx-analytics</a></h3>

Risk and return for 22 liquid IDX stocks plus IHSG as benchmark. Five years of daily prices, ten metrics per ticker, four charts, one markdown report.

<p align="center">
  <a href="https://github.com/4RGY/ihsg-idx-analytics">
    <img src="https://raw.githubusercontent.com/4RGY/ihsg-idx-analytics/main/outputs/figures/01_risiko_imbal_hasil.png" width="47%" alt="Risk versus return scatter for 22 IDX stocks" />
  </a>
  <a href="https://github.com/4RGY/ihsg-idx-analytics">
    <img src="https://raw.githubusercontent.com/4RGY/ihsg-idx-analytics/main/outputs/figures/03_drawdown.png" width="47%" alt="Drawdown curve" />
  </a>
</p>

`CAGR` `volatility` `Sharpe` `Sortino` `beta` `max drawdown` `VaR 95%` `Calmar` `correlation` `monthly seasonality`

The interesting part is not the table, it is what the data says: 17 of 22 stocks had a negative Sharpe over the sample, coal and heavy equipment won by not following the index (ADRO correlation to IHSG: 0.36), and July was positive in every year observed.

<h3><a href="https://github.com/4RGY/cuaca-indonesia">cuaca-indonesia</a></h3>

BMKG weather forecast for 19 cities, from Banda Aceh to Jayapura. Heatmaps of rain per city per day, felt temperature ranges, and early warnings for heavy rain slots above 20 mm per 3 hours.

<p align="center">
  <a href="https://github.com/4RGY/cuaca-indonesia">
    <img src="https://raw.githubusercontent.com/4RGY/cuaca-indonesia/main/outputs/figures/01_curah_hujan_kota.png" width="60%" alt="Total rainfall per city" />
  </a>
</p>

Getting BMKG data is the hard part: the API sits behind Cloudflare and rejects library TLS fingerprints, so the fetch layer uses `curl_cffi` with Chrome impersonation and the dotted `adm4` region code format. 19 cities, 375 forecast slots, 16 offline tests.

<h3><a href="https://github.com/4RGY/gempa-indonesia">gempa-indonesia</a></h3>

BMKG earthquake catalogue analysis: cleaning the free-text fields BMKG returns (`5,4` / `74 km` / `8.09 LS`), descriptive stats, Gutenberg-Richter b-value with the Aki-Utsu estimator and maximum curvature Mc, and a seismic energy balance converted to joules and TNT equivalent.

<p align="center">
  <a href="https://github.com/4RGY/gempa-indonesia">
    <img src="https://raw.githubusercontent.com/4RGY/gempa-indonesia/main/outputs/01_timeline_magnitudo.png" width="60%" alt="Earthquake timeline by magnitude" />
  </a>
</p>

The README snapshot block rewrites itself on every run, so the numbers you see are from the last fetch, not from my memory. 9 offline tests, refresh every hour.

## Other work

| Repo | Focus |
| :--- | :--- |
| [transjakarta-analysis](https://github.com/4RGY/transjakarta-analysis) | EDA of Transjakarta BRT transactions: routes, peak hours, passenger mix |
| [pendidikan-indonesia](https://github.com/4RGY/pendidikan-indonesia) | Indonesian education indicators 2017 to 2023: HDI, years of schooling, unemployment, school infrastructure |
| [kataloji-crm](https://github.com/4RGY/kataloji-crm) | Full CRM plus POS build, deployed and used for a real coffee shop |
| [alio-desktop](https://github.com/4RGY/alio-desktop) | Electron desktop companion app with local RAG modules |
| [freelance-toolkit](https://github.com/4RGY/freelance-toolkit) | Rate cards, invoices, and a job digest pipeline for freelance work |

## How I work

- **Reproducible over impressive.** A pipeline that reruns cleanly beats a notebook with a screenshot.
- **Tests without network.** Parsers and metric functions get unit tests, so CI runs even when the upstream API is down.
- **Honest numbers.** If the sample is small or the assumption is shaky, it goes in the limitations section, not in a footnote nobody reads.
- **Indonesian data first.** Local context is the whole point. BMKG, IDX, BPS, Dinkes, real cities, real names.

## Stack

**Data**
![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![pandas](https://img.shields.io/badge/pandas-150458?style=flat-square&logo=pandas&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-013243?style=flat-square&logo=numpy&logoColor=white)
![matplotlib](https://img.shields.io/badge/matplotlib-11557C?style=flat-square&logo=python&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=flat-square&logo=scikitlearn&logoColor=white)

**Web**
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white)
![Next.js](https://img.shields.io/badge/Next.js-000000?style=flat-square&logo=next.js&logoColor=white)
![Astro](https://img.shields.io/badge/Astro-BC52EE?style=flat-square&logo=astro&logoColor=white)
![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-38B2AC?style=flat-square&logo=tailwind-css&logoColor=white)
![Flask](https://img.shields.io/badge/Flask-000000?style=flat-square&logo=flask&logoColor=white)

**Tooling**
![Git](https://img.shields.io/badge/Git-F05032?style=flat-square&logo=git&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=flat-square&logo=githubactions&logoColor=white)
![pytest](https://img.shields.io/badge/pytest-0A9EDC?style=flat-square&logo=pytest&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-FCC624?style=flat-square&logo=linux&logoColor=black)

## Activity

<p align="left">
  <img src="https://github-readme-stats.vercel.app/api?username=4RGY&show_icons=true&theme=dark&hide_border=true&hide_title=true" alt="GitHub stats" height="150" />
  <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=4RGY&layout=compact&theme=dark&hide_border=true&langs_count=8" alt="Top languages" height="150" />
</p>

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/4RGY/4RGY/output/github-contribution-grid-snake-dark.svg" />
  <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/4RGY/4RGY/output/github-contribution-grid-snake.svg" />
  <img alt="Contribution grid snake" src="https://raw.githubusercontent.com/4RGY/4RGY/output/github-contribution-grid-snake.svg" />
</picture>

---

<div align="center">

**Open for freelance work**: data pipelines, dashboards, bots, and small web apps.

[argyang77@gmail.com](mailto:argyang77@gmail.com) &nbsp;·&nbsp; [angg4ra.my.id](https://angg4ra.my.id)

</div>
