__Attribute__ – column

__Tuple__ – row, record

__Field__ – cell

__Data domain__ – range of possible values (all the values which a data element may contain) of an attribute

__Candidate key__ – one or more attributes that are non-empty (have values) and don't repeat inside a table (unique value for each tuple). Unique set of prime attributes

__Prime attribute__ – an attribute that is a part of any candidate key

__Primary key__ – a candidate key that is most suitable for the purpose of being primary. Usually with the least number of attributes or / and with the smalles memory footprint

## 1NF
To be in the first normal form:
1. Domain of each attribute should contain only atomic values
2. Each field should contain a single value from its data domain (no lists of values in one field)
3. The table must have a primary key

## 2NF
To be in the second normal form:
1. The table must be in the 1NF
2. All non-primary attributes in a table must functionally depend on a the whole of every candidate key (attributes can't partially depend on the candidate keys)
    * If primary key is not compound, that table already satisfies that requirment
    * If any attribute depends only on a part of a primary key, an according attribute should be extracted to a separate table. If an attribute A functionally depends on the whole of B, than A can always be found if B is given
