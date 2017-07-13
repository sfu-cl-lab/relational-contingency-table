# relational-contingency-table
Computes contingency tables for relational databases, i.e. counts across tables

## Input

+ A relational database  `data-db`
+ A metadata database `setup-db`
+ An output database `ct-db`
+ A list of first-order terms (aka functor nodes, first-order random variables) stored in the table `setup-db.FunctorSet`
+ Optional: A list of first-order variables stored in the table `setup-db.FunctorSet`


## output

A table `ct-db.ct-table` of the form (fill in table format exaple) where

+ a row lists a combination of possible values for each first-order term
+ `count` gives the number of database instances where each first-order term is assigned the value in the row. `Count` is the size of the result set of the database query defined by the conjunction of literals term = value.
+ If first-order variables are specified, the contingency tables gives counts for each grounding or instantiation of the first-order variables with constants denoting individuals. 

## References

The algorithm implements the method from (Qian et al.) based on metaqueries and the Inverse Fast Moebius Transform.
