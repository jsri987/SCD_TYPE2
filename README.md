# SCD_TYPE2
SCD type2 implementation

PL/SQL implementation of SCD type 2. 
One current and history tables are maintained in the schema for each entity, the SCD implementation is done via triggers.
Every insert and update in the current table triggers an insert in the history table. 
End date of the each inserted record in the history table is '12-31-9999'.

For each update post an insert merge is triggered to compute the end date of records by using a lead function.
The latest record would have an end date of NULL. A case statement is added to set the end date as '12-31-9999'.
