# arXiv metadata mirror

This is a mirror of the meta of preprints at https://arxiv.org, as provided by the [OAI API](https://arxiv.org/help/oa/index) in `oai_dc` format.

Downloading full dataset from the API is a very slow (due to heavy rate limiting) and laborious process (outdated python bindings).
We think that git provides a much nicer way to share data sets of limited size (<1Gb) like this one.

## Data Structure

- One file per day. The release schedule of the arxiv is one per day, so a finer granularity does not make sense.
- Files are immutable. Once written they are not changed by subsequent updates. This avoids versioning overhead in git.
- One JSON record per line. Newlines in JSON strings have to be escaped, hence we can store all JSON objects in a single line.
- Fields in jq path notation:
  - `.[0]` arxiv ID
  - `.[1]` the oai_dc JSON document returned by the API

Example Record

```
[ "0704.0004", {
  "contributor":[],
  "date":["2007-03-30"],
  "rights":[],
  "title":["A determinant of Stirling cycle numbers counts unlabeled acyclic\n  single-source automata"],
  "publisher":[],
  "identifier":["http://arxiv.org/abs/0704.0004"],
  "creator":["Callan, David"],
  "subject":["Mathematics - Combinatorics","05A15"],
  "description":["  We show that a determinant of Stirling cycle numbers counts unlabeled acyclic\nsingle-source automata. The proof involves a bijection from these automata to\ncertain marked lattice paths and a sign-reversing involution to evaluate the\ndeterminant.\n","Comment: 11 pages"],
  "language":[],
  "format":[],
  "type":["text"],
  "coverage":[],
  "source":[],
  "relation":[]}
]
```
## Missing files

The following files could not be downloaded. Still investigating.

* 2011-06-04
* 2010-10-05
* 2010-08-19
* 2010-06-28
* 2010-06-24
* 2010-06-22
* 2009-02-20
