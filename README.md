# sparql
A range of simple annotated SPARQL queries against skos-based vocabularies using the [GSQ vocabulary library](https://vocabs.gsq.digital) as example data. 
These principles can be applied to any vocabulary (taxonomy) or ontology. The queries here are meant to demonstrate the most basic SPARQL functions against a set of vocabularies (essentially simplified ontologies) to provide a tool to familiarise a user with the essentials of graph querying. To test the queres in this repository go to https://vocabs.gsq.digital/sparql/ to see the results.

**Disclaimer**
As of the time of writing (2022-12-12) I am not an expert on SPARQL. These queries serve to record what I know so far and to build out a library of queries as I learn how to make SPARQL do the things I want. Hopefully the annotation and examples provides some guidance to others learning this query langauge.

**Basic Notes**
- SPARQL nulls are different to SQL nulls. A null value in sparql will result in omission of the whole row. Therefore if you expect nulls to be present use an OPTIONAL clause. Further to this, if you bundle criteria within an OPTIONAL clause, it will check for _all_ those criteria to be true at once. So OPTIONAL {X=True; Y=True}; requires both to be true to get a result. If you want to return X if it exists against a subject, and Y if it exists against a subject as independent functions, use two separate OPTIONAL calls, i.e. OPTIONAL {X=True}; OPTIONAL {Y=True}; .
- The return labels are indicated by the _**?**_ prefix. For example, ?concepturi will return a column called concepturi. The queries in this repository use some personal conventions for naming parts of the vocabulary structure, but these can be named whatever you want, e.g. what I declare as ?concepturi can be named ?id, ?uri, ?pid or anything else. The ? function acts in the same manner as the AS function in SQL
