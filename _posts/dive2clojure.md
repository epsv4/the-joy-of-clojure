---
layout: default
title: divetoclojure
---
#destructuring
```
(def guys-name-map
  {:f-name "Guy" :m-name "Lewis" :l-name "Steele"})
(let [{f-name :f-name1} guys-name-map]
  (println f-name))
;destructing key words :as :keys :or :syms
(let [{:keys [f-name m-name]} guys-name-map]
  (println (str f-name " " m-name)))
(let [{first-thing 0, last-thing 3} [1 2 3 4]]
  [first-thing last-thing])
;key word function definition
;Note that when defined this way, whole-name isn¡¯t called with a map parameter, but
;rather with arguments that alternate between keys and values.
;Using a map to destructure this list of arguments causes the list to first be poured into a map collection
;before then being destructured as usual.
(defn whole-name [& args]
  (let [{:keys [f-name m-name l-name]} args]
    (str l-name ", " f-name " " m-name)))
;One final technique worth mentioning is associative destructuring.
(let [{first-thing 0, last-thing 3} [1 2 3 4]]
  [first-thing last-thing])
```