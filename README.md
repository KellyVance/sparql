# sparql
A range of simple annotated SPARQL queries against skos-based vocabularies using the publicly accessible [GSQ vocabulary library](https://vocabs.gsq.digital) as example data. To test the queres in this repository go to https://vocabs.gsq.digital/sparql/ and past in the queries to see the results.

These principles can be applied to any resource description framework (RDF) vocabulary/taxonomy or ontology. The queries here are meant to demonstrate basic SPARQL functions against a set of vocabularies (essentially simple ontologies) to provide a tool to familiarise users with the essentials of graph querying. 

Numbering of the sparql files only indicates perceived complexity and progression of function specificity.

**Disclaimer**
As of the time of writing (2022-12-22) I am not an expert on SPARQL. These queries serve to record what I know so far and to build out a library of queries as I learn how to make SPARQL do the things I want. The intent is for the annotation and examples to provide guidance to others learning this query langauge in a simplified and plain language manner.

**Basic Notes**
- SPARQL nulls are different to SQL nulls. A null value in sparql will result in omission of the whole row. Therefore if you expect nulls to be present use an OPTIONAL clause. Further to this, if you bundle criteria within an OPTIONAL clause, it will check for _all_ those criteria to be true at once. So OPTIONAL {X=True; Y=True}; requires both to be true to get a result. If you want to return X if it exists against a subject, and Y if it exists against a subject as independent functions, use two separate OPTIONAL calls, i.e. OPTIONAL {X=True}; OPTIONAL {Y=True}; .
- The return labels are indicated by the _**?**_ prefix. For example, ?concepturi will return a column called concepturi from the criteria defined in the query. The queries in this repository use some personal conventions for naming parts of the vocabulary structure, but these can be named whatever you want, e.g. what I declare as ?concepturi can be named ?id, ?uri, ?pid or anything else. The _?_ function acts in the same manner as the _AS_ function in SQL
