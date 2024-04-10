# Streamlit and Python Packages

This page shares an example of work where I have used Python packages and Streamlit.

> ⭐ **Relevant experience to STARS:**
> * **Python packages** (WP1, restructuring into reproducible software package)
> * **Streamlit** (sharing a model using a web app)

## Context

Delivering a wellbeing survey with secondary school pupils at nine schools across North Devon and Torridge. There are two survey types:
* **Standard** survey for mainstream schools
* **Symbol** survey for special schools

We do not yet have results, but I have prepared dashboards using synthetic data. The purpose of these dashboards is:
* To share a schools results back with them (with standard and symbol survey dashboards, specific to each school)
* Public dashboards to share results across Northern Devon (e.g. Public Health team, community partners on Kailo)

The dashboards are produced in Python using streamlit.

## Package

Due to overlap between dashboards, create a package for reuse of code.

[Package on GitHub:](https://github.com/kailo-beewell/kailo_beewell_dashboard_package)

![Screenshot of package on GitHub](img/kailo_package_github.png)

[Package on PyPI:](https://pypi.org/project/kailo-beewell-dashboard/)

![Screenshot of package on PyPI](img/kailo_package_pypi.png)

[Package documentation:](https://kailo-beewell-dashboard.readthedocs.io/en/latest/)

![Screenshot of documentation](img/kailo_package_docs.png)

## Example: School dashboard (standard survey)

[![Open in Streamlit](https://static.streamlit.io/badges/streamlit_badge_black_white.svg)](https://synthetic-beewell-kailo-standard-school-dashboard.streamlit.app)

Features include:
* User authentication
* Importing data hosted within TIDB cloud
* Generation of a static PDF report

Hosted on Streamlit Community Cloud

<iframe style="display: block; margin: auto;" src="https://synthetic-beewell-kailo-standard-school-dashboard.streamlit.app/?embed=True" height="800" width="80%"></iframe>

## Example 2: Northern Devon dashboard

[![Open in Streamlit](https://static.streamlit.io/badges/streamlit_badge_black_white.svg)](https://synthetic-beewell-kailo-public-dashboard.streamlit.app/)

<iframe style="display: block; margin: auto;" src="https://synthetic-beewell-kailo-public-dashboard.streamlit.app/?embed=True" height="800" width="80%"></iframe>