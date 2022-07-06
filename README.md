# CMG UW - Whistle Projector for FHIR
CMG UW Whistle Projectors to Load Data into FHIR

This repository contains the components specifically designed for ingesting CMG UW into FHIR using the python pipeline application, [NCPI Whistler](https://github.com/NIH-NCPI/ncpi-whistler). Whistler is a pipeline designed to do several things:
* Transform CSV Harmony files into Concept Maps (these are used by Whistle to transform data to standard codings)
* Transform CSV dataset files and data-dictionaries into JSON file to be processed by whistle code
* Automate the execution of Whistle
* Process JSON output from Whistle and ingest into or validate against a FHIR server

Whistler is currently a single app, but is built in a modular fashion so that, if we decided to employ it within a cloud context, it's various functions can be used independantly alongside traditional cloud functionality. 

## Whistle
[Whistle](https://github.com/GoogleCloudPlatform/healthcare-data-harmonization) is a language developed for the purposes of transforming files from one form of JSON into another. For the purposes of ingesting CMG data into FHIR, we transform the CSV input into JSON objects and then tranform those into JSON suitable for passing the a FHIR REST Api endpoint. The language is concise and specific to this purpose and is therefore easy to read and not difficult to write. 

One of the strongest features built into Whistle is the use of FHIR [ConceptMaps](http://hl7.org/fhir/R4/conceptmap.html) to transform data from one terminology to another easily. This is a core aspect of the data harmonization part of the system's name and is central to the language itself. 

## Current Limitations
There are some issues that will be added to the issues of this repository that relate to current design limitations or our current understanding of the current data model. Included in these is the potentially incomplete mapping to public ontologies and the fact that our current Implementation Guide (IG) is still a work in progress and may evolve into something different from what these whistle files are based on. 

