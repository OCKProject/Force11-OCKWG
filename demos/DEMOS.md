# Demonstrations of automated literature search and analysis

To analyse the hundreds of thousands of articles on climate change we have created Open Source tools for automated:

* downloading
* searching by keywords
* display 

of Open Access articles in repositories. These demos have a very small subset of the available material but shouled be enough to illustrate the approach.

All analysis is done on the client side, and if you wish to do this yourself you'll need to install the software and reserve diskspace for your downloaded articles.

## Repositories

**NOTE: This is not a detailed tutorial; we'll add that later.**

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
ami-search -

[Output for epmc250](../demos/epmc250/).







