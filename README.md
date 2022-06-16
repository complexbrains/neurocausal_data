# NeuroCausal: data-storage

In this repository we will be listing the parametric files that is required for the analysis pipeline to run. 
We will also share the OSF link to the downloaded open access clinical papers that will be used in [NeuroCausal](https://github.com/neurocausal/neurocausal) pipeline.

The dataset will be periodically updated as the new bunch of data added and new features are extended to the tool.



The current data resides in [NeuroCausal OSF Repository](https://osf.io/hjsm2/) for a specific queries (_aphasia + neurodegeneration_ and _aphasia + fMRI_ ) we run with [NeuroQuery pipeline](https://github.com/neuroquery/nqdc). 


The data folder structure of the shared data is:

```
query-aphasia_neurodegenerative.zip
  └── query-aphasia_neurodegenerative
      ├── articlesets
      │   ├── articleset_00000.xml
      │   └── info.json
      └── articles
          ├── 000
          │   └──pmcid_4382926.xml
          ├── 00a
          │   └──pmcid_8317687.xml
          ├── 00b
          │   └── pmcid_6625472.xml
          ├── ...
          ├── e12
          │   ├── pmcid_8832765.xml
          ├── ...
          │
          └── info.json
          └── subset_extractedData
                 ├── authors.csv
                 ├── coordinates.csv
                 ├── info.json
                 ├── metadata.csv
                 └── text.csv
```

`articlesets` Folder contains the raw xml file that contains the bulk of papers downloaded with the query terms.
`articles` folder contains the xml file for the each papers downloaded.
`subset_allArticles_extractedData` folder contains the data separated into metadata specific individual csv files.

- `metadata.csv` contains one row per article, with some metadata: `pmcid`
  (PubMed Central ID), `pmid` (PubMed ID), `doi`, `title`, `journal`,
  `publication_year` and `license`. Note some values may be missing (for example
  not all articles have a `pmid` or `doi`).
- `authors.csv` contains one row per article per author. Fields are `pmcid`,
  `surname`, `given-names`.
- `text.csv` contains one row per article. The first field is the `pmcid`, and
  the other fields are `title`, `keywords`, `abstract`, and `body`, and contain
  the text extracted from these parts of the article.
- `coordinates.csv` contains one row for each `(x, y, z)` stereotactic
  coordinate found in any article. Its fields are the `pmcid` of the article,
  the table label and id the coordinates came from, and `x`, `y`, `z`.
