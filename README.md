# 🧩 eLTER-RI Controlled Vocabulary – Controlled Lists (CL)

[![FAIR RDF Generation](https://github.com/LTER-Europe/elter_cl/actions/workflows/sheet2rdf.yml/badge.svg?branch=main)](https://github.com/LTER-Europe/elter_cl/actions/workflows/sheet2rdf.yml)

The **Controlled Lists (CL)** vocabulary provides a collection of standardised term lists used across the [eLTER Research Infrastructure](https://elter-ri.eu/).  
It supports interoperability and harmonisation of metadata across eLTER components such as [DEIMS-SDR](https://deims.org), the eLTER Data Portal, and other services of the eLTER Cyberinfrastructure.  

The CL vocabulary includes domain-specific value lists (e.g., ecosystem types, sampling methods, observation categories) that ensure consistency in describing environmental data and research sites across Europe.  
It is an essential component of the eLTER semantic ecosystem, enabling **FAIR, machine-actionable, and interoperable metadata**.

📘 **Vocabulary access:** [https://vocabs.lter-europe.net/elter_cl/en/](https://vocabs.lter-europe.net/elter_cl/en/)

---

## ⚙️ Automated FAIR Workflow — *sheet2rdf*

This repository is automatically updated through the [**sheet2rdf**](https://github.com/nikokaoja/sheet2rdf) workflow, which ensures that the vocabulary remains FAIR and synchronised with its authoritative Google Sheet source.

The workflow automatically:

1. Fetches the Google Sheet source as `.xlsx` and `.csv` files  
2. Converts the sheet to RDF (Turtle) using [**xls2rdf**](https://github.com/sparna-git/xls2rdf)  
3. Commits the generated `.ttl`, `.xlsx`, and log files to this repository  
4. Publishes the resulting RDF to the [**Skosmos vocabulary server**](https://vocabs.lter-europe.net)

This workflow extends [**excel2rdf**](https://github.com/fair-data-collective/excel2rdf-template) and is licensed under the [Apache 2.0 License](https://github.com/nikokaoja/sheet2rdf/blob/main/License.md).

🧾 **Workflow provenance:**  
> This file has been modified from its originally licensed version by *WillOnGit* – see [README.md](https://github.com/LTER-Europe/CL) at repository root for license information.

📚 **Citation:**  
> Nikola Vasiljevic. (2021, January 11). *sheet2rdf: First release* (Version v0.1). Zenodo. [https://doi.org/10.5281/zenodo.4432136](https://doi.org/10.5281/zenodo.4432136)

---

## 🧠 Repository contents

| File | Description |
|------|--------------|
| [elter_cl.ttl](https://github.com/LTER-Europe/eLTER_CL/blob/main/elter_cl.ttl) | RDF (Turtle) representation of the eLTER Controlled Lists vocabulary |
| [elter_cl.xlsx](https://github.com/LTER-Europe/eLTER_CL/blob/main/elter_cl.xlsx) | Source spreadsheet fetched from Google Sheets |
| [elter_cl.csv](https://github.com/LTER-Europe/eLTER_CL/blob/main/elter_cl.csv) | CSV export of the vocabulary |
| [logs/](https://github.com/LTER-Europe/eLTER_CL/tree/main/logs) | Conversion logs produced during RDF generation |
| [.github/workflows/sheet2rdf.yml](https://github.com/LTER-Europe/eLTER_CL/blob/main/.github/workflows/sheet2rdf.yml) | GitHub Action workflow automating the FAIR publication process |

---

## 🧭 Acknowledgements

This work builds on the efforts of the [eLTER-RI](https://elter-ri.eu/) communities, with support from multiple projects contributing to the development of interoperable and FAIR semantic resources for environmental research infrastructures.

---

## 💡 Related vocabularies

| Vocabulary | Description | Access |
|-------------|--------------|--------|
| **[SO – Standard Observations](https://github.com/LTER-Europe/SO)** | Controlled vocabulary describing eLTER Standard Observations (SOs) variables, methods, and protocols | [View in Skosmos](https://vocabs.lter-europe.net/so/en/) |
| **[EnvThes – Environmental Thesaurus](https://github.com/LTER-Europe/EnvThes)** | Common semantic framework for environmental parameters and concepts | [View in Skosmos](https://vocabs.elter-ri.eu/EnvThes/en/) |
