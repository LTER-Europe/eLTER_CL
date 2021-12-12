<img src="https://www.lter-europe.net/logo.jpg" alt="incentive logo" width="250"/> 

[![CI](https://github.com/LTER-Europe/eLTER_CL/workflows/Sheet2RDF/badge.svg)](https://github.com/LTER-Europe/eLTER_CL/actions?query=workflow%3ASheet2RDF)

# [eLTER_CL](http://purl.org/eLTER_CL/)
eLTER_CL is a thesaurus for controlled lists used by the eLTER community. 

`sheet2rdf` and `OntoStack`, developed by Nikola Vasiljevic, are used to build and serve **eLTER_CL**, while [PURL](https://archive.org/services/purl/) is used to persist identifiers for the thesaurus terms:

   http://purl.org/eLTER_CL/


# Tooling

## [![DOI](https://zenodo.org/badge/327900313.svg)](https://zenodo.org/badge/latestdoi/327900313) sheet2rdf

This repository hosts automatic workflow, executed by means of Github actions, and underlying shell and python scripts which:

- Fetches Google Sheet from Google Drive and stores is as `xlsx` and `csv` files
- Converts fetched sheet to machine-actionable and FAIR RDF vocabulary using [xls2rdf](https://github.com/sparna-git/xls2rdf)
- Tests the resulting RDF vocabulary using [qSKOS](https://github.com/cmader/qSKOS/)
- Commits conversion results and tests logs to this repository
- and deploy RDF vocabulary to OntoStack to be served to humans and machines

This workflow is an extension of [excel2rdf](https://github.com/fair-data-collective/excel2rdf-template).


### Configuring sheet2rdf

In case you want to use **sheet2rdf** in your own work you need to:

1. Follow [gsheets](https://pypi.org/project/gsheets/) Quickstart and generate client_secrets.json and storage.json

2. Create following [Github secrets](https://docs.github.com/en/free-pro-team@latest/actions/reference/encrypted-secrets):

| Secret | Explanation | eLTER_CL onfiguration |
|---|---|---|
| DB_USER | user name of Jena Fuseki user account that has privilages to PUT RDF vocabulary to the database | ******** |
| DB_PASS | password of for the above account Jena Fuseki account | ******** |
| FILE_NAME | file name that will be used when converting Google sheet to `.ttl` (RDF), `.xlsx`, and `.csv` files | vocabulary |
| GRAPH | graph in the database under which the above RDF vocabulary should be stored | http://purl.org/eLTER_CL/ |
| SHEET_ID | unique ID of the sheet that will be fetched from Google drive | [1yojSDLy4Iw8GFR2ZX7b9T8kb8As6XUij5jU8KKvEicg](https://docs.google.com/spreadsheets/d/1yojSDLy4Iw8GFR2ZX7b9T8kb8As6XUij5jU8KKvEicg/edit#gid=1198865354) |
| SPARQL_ENDPOINT | endpoint to which RDF vocabulary is PUT | ******** |
| STORAGE | access token to Google Drive hosting Google sheet with controlled terms definitions, content of client_secret.json | ******** |
| CLIENT | configuration for client (i.e., sheetrdf) that is fetching Google sheet, content of storage.json | ******** |

### Citation

In case you are using this workflow the author kindly requests you to cite this repository in your publications such as:
> Nikola Vasiljevic. (2021, January 11). sheet2rdf: First release (Version v0.1). Zenodo. http://doi.org/10.5281/zenodo.4432136

For any other citation format visit http://doi.org/10.5281/zenodo.4432136

## OntoStack

OntoStack is a set of orchestrated micro-services configured and interfaced such that they can intake vocabularies and resolve their terms and RDF properties upon requests either by humans or machines.

Some of OntoStack micro-services are:

- [Jena Fuseki](https://jena.apache.org/documentation/fuseki2/) a graph database
- [SKOSMOS](http://www.skosmos.org/) a web-based SKOS browser acting as a front-end for the vocabularies persisted by the graph database
- [Træfik](https://doc.traefik.io/traefik/) an edge router responsible for proper serving of URL requests

Currently three instances of OntoStack are available:

- Departamental instance of [DTU Wind Energy](https://www.vindenergi.dtu.dk/english/): http://data.windenergy.dtu.dk/ontologies
- National (Danish) instance ran by [DeiC](https://deic.dk/): http://ontology.deic.dk/
- International instance ran by [FAIR Data Collective](http://fairdatacollective.org/): http://vocab.fairdatacollective.org


# License

- Tech configuration (sheet2rd) is licensed under [Apache 2.0 License](https://github.com/LTER-Europe/eLTER_CL/blob/main/License_sheet2rdf.md)
- Theasurus is licensed under [CC0 1.0 Universal](https://github.com/LTER-Europe/eLTER_CL/blob/main/LICENSE)
