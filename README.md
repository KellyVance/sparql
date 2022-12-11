# sparql
A range of annotated basic SPARQL queries against skos-based vocabularies using the GSQ vocabulary library as example data https://vocabs.gsq.digital

Basic Notes
- SPARQL nulls are different to SQL nulls. A null value in sparql will result in the whole row being omitted. Therefore where you expect nulls to be present use an OPTIONAL clause. Further to this is you bundle criteria in an OPTIONAL clause it will check for all those criteria to be true at once. So Optional {X=True; Y=True; requires both to be true at once to get a result. If you want to return X if it exists, and Y if it exists independently use two separate OPTIONAL calls, i.e. OPTIONAL {X=True}. OPTIONAL {Y=True}
The return labels are indicated by the _**?**_ prefix e.g. ?concepturi will return in a column called concepturi. The queries in this repository use some personal conventions for naming parts of the vocabulary structure, but these can be named whatever you want. The ? function acts in the same manner as the AS function in SQL
