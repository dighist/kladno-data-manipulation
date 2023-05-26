# Kladno Data Manipulation

This repository collects different scripts that are used to manipulate data for the Kladno Archive.

## kladno_sanity_import_preparation

This script takes a folder of case documents as input inside the `input` folder.
The this folder needs to have the following structure:

```
KLID Sanity Cases
│
└─── / 1375_Božena Berdychová_Oú Kladno_Karton_1446_Sign._17-2B // 1. Case
      │
      └─── Božena Bedrychová (1) // First document, as a folder of pages
      │    │
      │    └─── Božena Bedrychová (1+2).JPG // first page of the document
      │    └─── Božena Bedrychová (3) // second page of the document
      │
      └─── Božena Bedrychová (6).JPG // Second document, single page        
```

Adjust the following paths at the top of the script 

```
# The path to the input
SANITY_CASES_FILE_PATH = 'input/KLID Sanity Cases' 
# Absolute path to the script
ABSOLUTE_PATH_TO_HERE = '/Users/{your_user}/path/to/kladno-data-manipulation/'
```

Then run `poetry run python kladno_sanity_import_preparation.py`.

This will generate the file `sanity_cases.ndjson` inside `./output`.

You can then use this file to make a bulk import into sanity using the sanity CLI, check this [documentation](https://www.sanity.io/docs/importing-data)