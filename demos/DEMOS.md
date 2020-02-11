# Demonstrations of automated literature search and analysis

To analyse the hundreds of thousands of articles on climate change we have created Open Source tools for automated:

* downloading
* searching by keywords
* display 

of Open Access articles in repositories. These demos have a very small subset of the available material but should be enough to illustrate the approach.

All analysis is done on the client side, and if you wish to do this yourself you'll need to install the software and reserve diskspace for your downloaded articles.

## Repositories

*NOTE: This is not a detailed tutorial; we'll add that later.*

### EuropePMC
This is a European version of PubMedCentral and uses the EPMC server to download in bulk. We use `getpapers` (see https://github.com/contentmine/getpapers) , developed by Rik Smith-Unna for 
contentmine.org which issues a query, retrieves the metadata and then downoads variants of the fulltext,
We issued the command:
```
getpapers --query "climate change" --output epmc250 --xml --limit 250
```
which stores up to 250 articles fitting the query "climate change", in XML in directory `epmc250/`. 

We then run [AMI](https://github.com/petermr/ami3) with the command:
```
ami-search -p epmc250 --dictionary country funders ...
```
which queries the articles with dictionaries for `country`, funders` (and several more).

#### outputs

[spreadsheet (`full.dataTables.html`)](http://htmlpreview.github.io/?https://github.com/OCKProject/Force11-OCKWG/blob/master/demos/epmc250/full.dataTables.html)

for dictionary searches on `empc250`. The dictionaries are the column headings while the articles are rows.




[Output for epmc250](../demos/epmc250/).

### biorxiv

[Biorxiv](https://biorxiv.org) is a preprint server for biosciece articles run from Cold Spring Harbor laboratories and offering Open Access preprints.

NOTE: this is a very preiminary result and details of the search are not given. In essence it follows the `getpapers` strategy (but uses `curl`) to issue a query, download the ResultSet of metadata, create landing pages for each and then issues requests for the fulltext in HTML.

#### outputs

*  [**result set**](http://htmlpreview.github.io/?https://github.com/OCKProject/Force11-OCKWG/blob/master/demos/biorxiv250/__metadata//resultSet1.clean.html)

* [spreadsheet (`full.dataTables.html`)](http://htmlpreview.github.io/?https://github.com/OCKProject/Force11-OCKWG/blob/master/demos/biorxiv250/full.dataTables.html)



[Output for biorxiv250](../demos/biorxiv250/).

## Interpretation of searches

Each search returns:

* global metadata (describing the whole search, e.g. number of hits and overview)
* a directory for each article, with a unique ID (either PMCID or doi)
* within the directory 
  - metadata for the article
  - fulltext (XML, PDF or HTML)
* transformed material, (searches, extractions, sectioning, etc.)
* 





