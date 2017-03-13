
We'll spend more time on vectors and maps than on the other types, because those two are used in a wider variety of circumstances and warrant the extra discussion
#Persistence, sequences, and complexity
Clojure¡¯s collection data types have some unique properties compared to collections in many mainstream languages. Terms such as persistent and sequence come up, and not always in a way that makes their meaning clear. In this section, we¡¯ll define their meanings carefully. We¡¯ll also briefly examine the topic of algorithmic complexity and Big-O notation as they apply to Clojure collections.
The term persistent is particularly problematic because it means something different in other contexts. In the case of Clojure, we believe that a phrase immortalized by Inigo Montoya from the novel and subsequent film The Princess Bride summarizes your likely initial reaction
The original vector ds did not change on the replacement of the keyword :barnabas
but instead created another vector with the changed value. A natural concern when
confronted with this picture of persistence is that a naive implementation would copy
the entire collection on each change, leading to slow operations and poor use of
memory. Clojure¡¯s implementations (Bagwell 2001) are instead efficient by sharing
structural elements from one version of a persistent structure to another. This may
seem magical, but we¡¯ll demystify it in the next chapter.
A sequential collection is one that holds a series of values without reordering them. As
such, it¡¯s one of three broad categories of collection types along with sets and maps.
A sequence is a sequential collection that represents a series of values that may or
may not exist yet. They may be values from a concrete collection or values that are
computed as necessary. A sequence may also be empty.
Clojure has a simple API called seq for navigating collections. It consist of two functions: first and rest. If the collection has anything in it, (first coll) returns the
first element; otherwise it returns nil. (rest coll) returns a sequence of the items
other than the first. If there are no other items, rest returns an empty sequence and
never nil. As you may recall from sections 3.1 and 3.2, the way that Clojure treats nil
versus empty collections motivates the iteration patterns used in the language. Clojure
functions that promise to return sequences, such as map and filter, work the same
way as rest. A seq is any object that implements the seq API, thereby supporting the
functions first and rest. You might consider it an immutable variant of an enumera