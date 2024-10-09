# MongoDB Indexes

> - Data structure that improves the efficiency of read operations
> - Can be created using one or more fields of the document
> - Without indexes, collection scan
> - With indexes, index scan

## Introduction
- Stores a small portion of collection’s data set
- Stores the value of specific field(s), ordered by the value of the field
- The ordering of the index supports:
  - efficient equality matches
  - range-based queries
  - Faster sort results
- It comes with:
  - Cost of additional writes
  - Additional storage space
- below diagram illustrates indexing    
![Example](mongoIndex.JPG)

### Types of Indexes
> ![Single Field Index](single-field-index.md)
  
> Compound Index

> Multikey Index

> Geospatial Index
> To support efficient queries of geospatial coordinate data, MongoDB provides two special indexes:
>> 2d Index
>> 
>> 2dsphere Index

> Text Index

> Hashed Index

> Wildcard Indexes
