#vectors
Vectors store zero or more values sequentially, indexed by number; they¡¯re a bit like
arrays but are immutable and persistent. They¡¯re versatile and make efficient use of
memory and processor resources at both small and large sizes.

##create
in many cases, you¡¯ll want to create a vector out of the contents of some other kind of collection
```clojure
(vec (range 10))
```