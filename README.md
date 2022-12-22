# CLA Summarization Project 

The client analyzes hundreds of new **collective labour agreements (CLA)** on an annual basis, in order to interpret practical impact and implement them if necessary. 

Due to the **high volume** (>30 / week) of these **extensive documents**, this is a time consuming process. The task of collecting and processing these new collective agreements needs to be **accelerated and automated**, in order to **enable proactive notification**. 

Using the available metadata and Artificial Intelligence (NLP) the **relevant information** will be **extracted** from the documents. The client needs this information in a **structured way**, so **integrations** with existing platforms and/or new **reporting** are possible.

## Getting Started

The **collective labour agreements (CLA)** are in *pdf* format and can be obtained from the following website: 

[CAO Zoeken](https://werk.belgie.be/nl/themas/paritaire-comites-en-collectieve-arbeidsovereenkomsten-caos/collectieve-4)

The **metadata** of these CLA's are compiled by the client and provided in a spreadsheet. This can be obtained as well from the above-mentioned website.

## Prerequisites

The things you need to have a copy of the project up and running on your local machine for development and testing purposes.

* Python 3.x (The ~Demo~ notebook was run on a virtual environment with Python 3.9.15)
* pandas
* sqlite3
* pdfminer.six
* Stanza NLP
* scikit-learn feature extraction
* scikit-learn cluster
* numpy
* NLTK
* xlsxwriter

## Installation

This step by step guide will get you to have the development environment up and running.

```
$ Create and activate your virtual environment
$ Install additional packages and libraries
$ Open the notebooks in a code editor of your choice running on the virtual environment you just created
```

## Usage

The ~Demo~ module can be run on a set of pdf files from one Joint Committee. It serves as *proof of concept* for a larger-scale pipeline process.

## Pipeline

1. Text Extraction
> The text from the pdf files are extracted using pdfminer.six and stored in a new column of a pandas dataframe along with the Joint Committee number and pdf filename.

2. Language Detection
> The pdf text is parsed using Stanza Language Detector and split into Dutch and non-Dutch (currently, all others are classified as French). Each one is stored in new columns respectively.

3. Clustering
> The Dutch text data is analyzed to find groups of *co-occurring words* and each document is classified into clusters.

4. Summarization
> Using a set of pre-defined keywords, documents in the first class/cluster are summarized using sentences with higher frequency of the keywords. 

## Deployment

The end-result is currently being deployed into a spreadsheet (Excel file).

## Contributors

1. [Olga Kuznetsova](https://github.com/OKquark)
2. [Marlon Tadeo](https://github.com/m9tadeo)
