# Data Architecture for Analysts
1. What is data architecture? The benefits of good architecture
	- Software architecture
	- Productivity, replicability, teamwork
2. Data in the wild vs data conforming to business logic
	- Data warehouses vs data lakes
	- The fallacy of schema free data
	- Schemas and metadata
3. Data modeling for business logic
	- Entity modeling
	- Basics of relational data
4. Relations between entities
	- tables, rows, columns, keys
	- joins
	- normal forms
5. Relations between observations
	- groups
	- times, intervals
	- spatial data
	- networked data
6. Represent data on your computer
	- Serialization: JSON, XML vs TXT
	- There is no such thing as plain text
	- RDBMS
	- Document stores?
	- columnar db?
	- The benefits of flat files
7. Common data operations
	- Speaking SQL
	- filter, aggregagate, join
	- Data profiling and cleaning
8. Design for posterity
	- DRY 
	- SOLID principles for data modeling
	- Single responsibility
	- Dependency inversion
9. Choose great keys
	- Verbose keys
	- Hierarchical keys
	- Entity Resolution
	- Names are not unique
	- Three steps: Normalize, Merge, Propagate
10. Performance
	- Searching and indexing. Building a key-value store
	- RDBMS
	- Distributed data stores. Sharding.
11. Appendix
	- Data structures: list, set, dictionary, table (data frame), tree
	- SQL
	- O(n) notation
	- Tools
