python-joern
==

Introduction
--

A thin python interface for joern and a set of useful utility
traversals.

*Warning*: if you are using the current master-branch, this library is
not for you as the master-branch already contains a python interface
to joern bundled with joern. This is the python interface for future
versions of joern (development branch).

Dependencies:
--

+ py2neo 1.6.1 (http://book.py2neo.org/en/latest/)
+ py2neo-gremlin (https://github.com/fabsx00/py2neo-gremlin/)


### Installation

	$ sudo pip2 install git+git://github.com/fabsx00/python-joern.git

### Example

The following is a simple sample script. It connects to the database
and runs a gremlin traversal to retrieve all node with attribute
'functionName' set to 'main'.

```lang-none

from joern.all import JoernSteps

j = JoernSteps()

j.setGraphDbURL('http://localhost:7474/db/data/')

# j.setStepsDir('Use this to inject custom steps')

j.connectToDatabase()

res =  j.runGremlinQuery('g.idx("nodeIndex")[[functionName:"main"]]')

for r in res:
    print r
```
