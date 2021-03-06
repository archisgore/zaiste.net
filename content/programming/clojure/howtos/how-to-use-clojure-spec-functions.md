+++
title = "How To Use Clojure.Spec for Functions"
[taxonomies]
topics = [ "Clojure"]
+++

```clj
(defn int-to-digits
  [number]
  (str number))
```

Function specifications (or specs) are defined with `s/fdef`.

```clj
(s/fdef int-to-digits
  :args (s/cat :number int?))
```

The function’s argument names and the keywords in the `:args` spec don’t have to match, it’s position based.

The `instrument` function can be now used to assert the `:args` spec:

```clj
(stest/instrument `int-to-digits)
```

The `:ret` spec can be used to provide a specification for the return value:

```clj
(s/fdef number-to-digits
  :args (s/cat :number int?)
  :ret (s/coll-of char? :kind set? :min-count 1))
```

The `:ret` spec can be checked with the `check` function.

```clj
(stest/check `number-to-digits)
```

