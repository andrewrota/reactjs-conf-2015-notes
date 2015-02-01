**Persistent, immutable**

Leave the original unchanged and return a new version

Interface vs. implementation.

They work via a property of structural sharing.  When you make new things you want to share as much of the old one as possible.  This is possible because of a Directed Acyclic Graph (DAG).

DAGs are academic: I want to model my appliaction as arrays and objects.  Traditional data structors for objects and arrays are not DAGs.

reTrieve can be used to model a list of values and key value pairs.  Index Trie.  Each node is an array of a fixed size.  The values of are in the leafs.

bitshifting and array lookups: js engines are good at that.

Hash trie: hash array mapped trie.

function hash(key: any): Number (32bit)

You only have to go until you get to a value node.


Identity, value, and time.

Object.observe() - if you can't keep track of all the possible the mutators, the least you can do is observe the mutation.

Object.observe() is difficult with nested properties.

Dirty flag. (boolean)



React's just the V in MVC...that's because we don't need an M.


Memoization

We can solve problems by removing complexity not adding it...and that's pretty awesome.
