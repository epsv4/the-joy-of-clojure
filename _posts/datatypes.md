#precision
##truncation
Truncation refers to limiting accuracy for a floating-point number based on a deficiency in the corresponding representation.
##Promotion
clojure is able to detect when overflow occurs and it promotes the value to a numberical representation that can accommodate larger values.
In many cases, promotion results in the usage of a pair of classes used to hold exceptionally large values.
This promotion in Clojure is automatic, because the primary focus is first correctness of numerical values, then raw speed.
##Overflow
Integer and long values in Java are subject to overflow errors. When a numeric calculation results in a value that¡¯s larger than 32 bits of representation will allow, the bits of storage wrap around. When you¡¯re operating in Clojure, overflow isn¡¯t an issue for most cases, thanks to promotion. But when you¡¯re dealing with numeric operations on primitive types, overflow can occur.