# Discrete-event simulation (DES) models

> ⭐ **Relevance to STARS:**
> * DES models.
> * Producing R packages.

## Example: Contributions on IPACS

In **March and April 2023**, I spent a little bit of time with Alison, **contributing to the DES model on IPACS** (Improving Patient flow between Acute, Community and Social care).

### Final model

Working through the code for the IPACS model, **rewriting and simplifying to improve clarity, adding comments and docstrings, and identifying and fixing bugs**, [as detailed here](https://github.com/AliHarp/IPACS_MODEL). This contributed to the final repository hosted with [NHS BNSSG Analytics](https://github.com/nhs-bnssg-analytics/ipacs-model):

![Screenshot of IPACS BNSSG GitHub repo](img/ipacs_bnssg.png)

### Example package

I also had a bit of time in which I was able to make an example of the conversion of part of the model (visit-based simulation) into an R package, as in [this repository](https://github.com/amyheather/ipacs):

![Screenshot of IPACS Package GitHub](img/ipacs_pkg_github.png)

This is supported by a website that provides an overview of how to run the model, and information about functions:

<iframe
  src="https://amyheather.github.io/ipacs/"
  style="width:100%; height:800px;"
></iframe>