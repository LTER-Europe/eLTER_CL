# 🧩 eLTER-RI Controlled Vocabulary – Controlled Lists (CL)

[![FAIR RDF Generation](https://github.com/LTER-Europe/CL/actions/workflows/sheet2rdf.yml/badge.svg?branch=main)](https://github.com/LTER-Europe/CL/actions/workflows/sheet2rdf.yml)

The **Controlled Lists (CL)** vocabulary provides a collection of standardised term lists used across the [eLTER Research Infrastructure](https://elter-ri.eu/).  
It supports interoperability and harmonisation of metadata across eLTER components such as [DEIMS-SDR](https://deims.org), the eLTER Data Portal, and other services of the eLTER Cyberinfrastructure.  

The CL vocabulary includes domain-specific value lists (e.g., ecosystem types, sampling methods, observation categories) that ensure consistency in describing environmental data and research sites across Europe.  
It is an essential component of the eLTER semantic ecosystem, enabling **FAIR, machine-actionable, and interoperable metadata**.

📘 **Vocabulary access:** [https://vocabs.lter-europe.net/cl/en/](https://vocabs.lter-europe.net/cl/en/)

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
| [eLTER_CL.ttl](https://github.com/LTER-Europe/CL/blob/main/eLTER_CL.ttl) | RDF (Turtle) representation of the eLTER Controlled Lists vocabulary |
| [eLTER_CL.xlsx](https://github.com/LTER-Europe/CL/blob/main/eLTER_CL.xlsx) | Source spreadsheet fetched from Google Sheets |
| [eLTER_CL.csv](https://github.com/LTER-Europe/CL/blob/main/eLTER_CL.csv) | CSV export of the vocabulary |
| [logs/](https://github.com/LTER-Europe/CL/tree/main/logs) | Conversion logs produced during RDF generation |
| [.github/workflows/sheet2rdf.yml](https://github.com/LTER-Europe/CL/blob/main/.github/workflows/sheet2rdf.yml) | GitHub Action workflow automating the FAIR publication process |

---

## 💬 Contributing

If you wish to propose new terms or suggest modifications to existing ones:

- Please create a [GitHub account](https://github.com/signup)  
- Open a new [issue](https://github.com/LTER-Europe/CL/issues) describing your proposal  
- Consult the project [Wiki page](https://github.com/LTER-Europe/CL/wiki) for detailed instructions

The Controlled Lists vocabulary is licensed under [**CC BY 4.0**](https://creativecommons.org/licenses/by/4.0/).

---

## 🧩 Configuring *sheet2rdf*

If you want to use **sheet2rdf** in your own work, follow these steps to configure it for your vocabulary repository:

1. Generate a [Google API key](https://developers.google.com/sheets/api/guides/authorizing#APIKey) with read-only access to Google Sheets.
2. Create the following [**GitHub Secrets**](https://docs.github.com/en/actions/security-guides/encrypted-secrets):

| Secret | Explanation | Example configuration for *eLTER_CL* |
|--------|--------------|--------------------------------------|
| `FILE_NAME` | Base name used for the generated `.ttl`, `.xlsx`, and `.csv` files | `vocabulary` |
| `SHEET_ID` | Unique ID of the Google Sheet to be fetched | [1yojSDLy4Iw8GFR2ZX7b9T8kb8As6XUij5jU8KKvEicg](https://docs.google.com/spreadsheets/d/1yojSDLy4Iw8GFR2ZX7b9T8kb8As6XUij5jU8KKvEicg/edit#gid=1198865354) |
| `GOOGLE_API_KEY` | Google API key with read access to the spreadsheet | `AIza...` |

The workflow will automatically:
- Fetch the content of the specified tab (`SHEET_TAB_NAME`) from the Google Sheet  
- Convert it into `.xlsx`, `.csv`, and `.ttl` formats  
- Commit the outputs and logs to this repository  
- Create a new tagged release in GitHub with extracted FAIR metadata

---

## 🧭 Acknowledgements

This work builds on the efforts of the [eLTER-RI](https://elter-ri.eu/) communities, with support from multiple projects contributing to the development of interoperable and FAIR semantic resources for environmental research infrastructures.
