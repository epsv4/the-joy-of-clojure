#precision
##truncation
Truncation refers to limiting accuracy for a floating-point number based on a deficiency in the corresponding representation.
##Promotion
clojure is able to detect when overflow occurs and it promotes the value to
a numberical representation that can accommodate larger values.
In many cases, promotion results in the usage of a pair of classes used to hold exceptionally large values.