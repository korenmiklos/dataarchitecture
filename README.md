# Data Architecture for Analysts
1. What is data architecture? The benefits of good architecture
	1.1. Software architecture
	1.2. Productivity, replicability, teamwork
2. Data in the wild vs data conforming to business logic
	2.1. Data warehouses vs data lakes
	2.2. The fallacy of schema free data
3. Data modeling for business logic
	3.1. Entity modeling
	3.2. Basics of relational data
4. Relations between entities
	4.1. tables, rows, columns, keys
	4.2. joins
	4.3. normal forms
5. Relations between observations
	5.1. groups
	5.2. times, intervals
	5.3. spatial data
	5.4. networked data
6. Represent data on your computer
	6.1. Serialization: JSON, XML vs TXT
	6.2. There is no such thing as plain text
	6.3. RDBMS
	6.4. Document stores?
	6.5. The benefits of flat files
7. Common data operations
	7.1. Speaking SQL
	7.2. Data profiling and cleaning
8. Design for posterity
	8.1. DRY 
	8.2. SOLID principles for data modeling
	8.3. Single responsibility
	8.4. Dependency inversion
9. Choose great keys
	9.1. Verbose keys
	9.2. Hierarchical keys
	9.3. Entity Resolution
	9.4. Names are not unique
	9.5. Three steps: Normalize, Merge, Propagate
10. Performance
	10.1. Searching and indexing. Building a key-value store
	10.2. RDBMS
	10.3. Distributed data stores. Sharding.
11. Appendix
	11.1. SQL
	11.2. O(n) notation
	11.3. Tools
