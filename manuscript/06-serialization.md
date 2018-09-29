# Represent data on your computer

In the examples of this book, I often present data in neatly formatted tables. But your computer doesn't understand tables. It understands bytes. Let's dive into how data may be represented on your computer. This is not only an implementation detail left to engineers. If you understand the basics about storing data in your computer's memory, hard drive and on the network, you can make your analysis faster and more storage efficient. More importantly, you can better work with others who may have a different computer system (different operation system, different database engine, etc).

The objectives or efficient data representation are to minimize space for storage, the time for looking up a piece in your dataset, the time for common operations on your entire dataset, and to maximize the ease of sharing and reusing your data by other people (including your future self). As computing resources become cheaper, the human element becomes the more urgent objective, so I will focus mostly on those.

## Data structures

D> Here or in appendix only?

- number
- string
- list
- dictionary

A __dictionary__ (a.k.a. associative array, struct, key-value store) is a collection of _keys_ and _values_, such as `{first_name: charles, last_name: jones}`. Here the keys are `first_name` and `last_name`, and the respective values are `charles` and `jones`. Each key can only appear once.

The purpose of a dictionary is to make it easy to look up values by their keys. Software implementations of dictionaries (such as `dict` in Python or `XXX` in R) make it extremely efficient and fast. The trick is to use _hash functions_ for keys (see methods box). Magically, you can find a key in a bounded amount of time, irrespective of the size of the dataset in which you are searching.

A> ## Methods aside
A> hash functions. 

- set
- tree
- table

A __table__ (a.k.a. dataframe, dataset)

An __array__ ()

## Serialization



JSON, XML vs TXT, CSV

- There is no such thing as plain text
- RDBMS
- Document stores?
- The benefits of flat files

## Glossary
hash function
: XX Most frequent implementations are MD5 (not secure, as it is possible to generate documents with identical MD5 hashes) and SHA1.