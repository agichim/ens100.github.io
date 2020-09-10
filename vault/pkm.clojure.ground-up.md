---
id: 8206f66c-0051-45b3-8963-d263558deed0
title: Clojure From the Ground Up
desc: ''
updated: 1599582696331
created: 1599582696331
nav_order: .3
---

# Clojure from the Ground Up

**Title:** Clojure from the Ground Up  
**Author:** Kyle Kingsbury  
**Link:** [Link](https://aphyr.com/tags/Clojure-from-the-ground-up)  

---

## Chapter 1

- Values (Nouns)
  - Nil - most basic value
  - True / false - bolleans
  - 0, 1, -47, 1/3 - numbers
  - "Hello World" - String

- Verbs
  - "inc" (increment) - points to a values
  - Reference to other values

- Sentences
  - Add "'" (eg. '"foo") and get back what you wrote (the expression or sentence)
  - Returns the text unchanged

- List
  - Lists can contain anything: Numbers, Strings, other lists
  - List order is innermost to outermost
  - Think of these as trees

## Chapter 2

- Integers
  - Long/MAX_VALUE
  - BigInt (for really big numbers)
  - Short/MAX_VALUE
  - byte/MAX_VALUE

- Fractional Numbers
  -  Floats us 32 buts and Doubles use 64 - Doubles are default
  -  Ratio (eg. 1/3) exact value

- Mathematical Operatoins
  - ```(+ 1  2)``` = 3 sames goes for (+ 1  2.0) 
  - = "are all things that follow the same? vs ==  "are the things the same but more loosely"
  - ```(<= 1 2 3)``` = true - numbers are in order
  - inc (increment) and dec (decrease?) will add or subtract 1 respectively

- Strings
  -  Can make almost anything into a string (symbols, booleans, numbers)
  -  ```(str "cat")``` = (str 'cat)
  -  Can concatenate (str "meow " 3 " times") = meow 3 times
  -  re-find look for occurrences in a string
    -  ```(re-find #"cat" "mystic cat mouse")``` = "cat
    - ```(re-find #"cat" "only dogs here")``` = nil
  - re-matches - you can extract particular parts of a string which match an expression

- Booleans and Logic
  - alse and nil are negative, all else true
  - (and ) = (and 1 2 3)
  - (or ) = (or false 2 3)
  - (not ) = (not nil)

- Symbols
  - bare strings of characters like foo or +
  - Symbols is to refer to things, to point to other values

- Keywords
  - :cat = keyword
  - these are specifically intended for use as labels or identifiers
  - Keywords are most useful when paired with other values in a collection, like a map

- Lists
  - Collection is a group of values Containers provide structure Elements or Members are inside of collections list is a type of collection
  - Use single quote to prevent lists being evaluated ’(1 2 3)
  - Conjoin lists ``` (conj ’(1 2 3) 4)``` => (4 1 2 3)
  - ```(first (list 1 2 3))``` = 1
  - ```(second (list 1 2 3))``` = 2
  - ```(nth (list 1 2 3) 2)``` = 2
    - nth gets the element of an ordered collection at a particular index, Zero indexed
  - Well suited for small collection or things that are read in linear order.

- Vectors
  -  [1 2 3] Don’t need to be quoted as they are evaluated differently from lists.
  - ```(vector 1 2 3)``` returns [1 2 3]
  - ```(vec (list 1 2 3))``` returns [1 2 3]
  - ```(conj [1 2 3] 4)``` returns [1 2 3 4]
  - first, second and nth work but nth is fast for vectors
  - (rest …) and (next …) returns everything but the first
  - rest returns () when done and next returns nil(count [1 2 3])
  - = ’(1 2 3) [1 2 3]) if they contain the same elements in the same order they are considered equal.

- Sets
  - Unordered collection of value - good for if you plan to ask questions like “does the collection have the number 3 in it?”
  - ```#{:a :b :c}``` => will not always be in the same order.
  - ```(sort #{:a :b :c})``` will return them in order
  - ```(conj #{:a :b :c} :d)```
  - Conjoining will only contain each element once and will discard repeats.
  - ```(disj #{“cow” “sheep”} #{“sheep”})``` will return cow as this is the disjoin of the sets.
  - ```(contains? #{1 2 3} 3)``` returns true
  - Make any collection a set with the keyword (set (1 2 3))

- Maps
  - Surrounded by curly braces {…} and filled with alternating keys and values.
  - ```(get {“cat” “meow” “dog” “woof”} “cat”)``` will return “meow”
  - ```(get {:a 1 :b 2} :c)``` - will return false
  - ```(get {:glinda :good} :wicked :not-here)``` can provide a default value as the 4th argument.
  - ```(assoc {:bolts 1088} :camshafts 3)``` add to a map with assoc
  - ```(assoc {:camshafts 3} :camshafts 2)``` if they key already exists the value will be overwritten.
  - ```(merge {:a 1 :b 2} {:b 3 :c 4})``` - this combines maps and will prefer values from the later maps.
  - ```(dissoc {:potatoes 5 :mushrooms 2} :mushrooms)``` will remove a key/value pair.


Wow, that was a lot to take in, luckily I did see there were a few good Cheat Sheets around so do not necessarily need to remember every single one by heart just yet.

This chapter focused on Functions, vars and other cool features which can be found in Clojure: 

## Chapter 3

- Let
   - Define a meaning for a symbol within a specific expression, using `let`.
  - ```(let [cats 5] (str "I have " cats " cats."))``` - this will replace the first cats with 5
  - `(let [+ -] (+ 2 3))` - the + will be replaced with - as it is saying let + be -
  - `(let [person  "joseph" num-cats 186] (str person " has " num-cats " cats!"))` - this is a multiple bindings
  - `(let [cats 3 legs (* 4 cats)]  (str legs " legs all together"))` - in this case it takes the first criteria and applies it and so on

- Functions
  - Almost all verbs in Clojure are functions
  - Functions represent unrealized computation: expressions which are not yet evaluated, or incomplete
  - shorthand for writing functions `#(+ % 1)` is equivalent to `(fn [x] (+ x 1))`

- Vars
  - Redefine symbols for everyone–even code that we didn’t write–we need a new construct: a mutable variable
  - `(def astronauts []) / (def astronauts ["Sally Ride" "Guy Bluford"])`
  - Redefining names in this way changes the meaning of expressions everywhere in a program, without warning

- Defining functions
  - `(def half (fn [number] (/ number 2)))`
  - `(defn half [number] (/ number 2))` - above is shortened
  - `(defn half ([]  1/2) ([x] (/ x 2)))` - when calling multiple items

- Cool features of Clojure
  - (fn? type) - Is it a function?
  - (doc type / type / name) - What does the documentation say?
  - (meta #'type) - What about type's meta data?
  - (source type) - What about the actual source code?

## Chapter 4

- Direct Approach
  - If want to increment [1 2 3] each by one, could not simply use `inc` need to use: [(inc (nth numbers 0)) (inc (nth numbers 1)) (inc (nth numbers 2))]

- Recursion
	- `(first [1 2 3])` = the first item
	- `(rest [ 1 2 3])` = all but the first item
	- `cons`, which says “make a list beginning with the first argument, followed by all the elements in the second argument eg. `(cons 1 [2])`
 	- `(defn inc-first [nums] (if (first nums)` ; If there's a first number, build a new list with cons (cons (inc (first nums)) (rest nums)) ; If there's no first number, just return an empty list  (list)))`

- map
	- function expresses a sequence in which each element is some function applied to the corresponding element in the underlying sequence. This idea is so important that it has its own name, in mathematics, Clojure, and other languages. We call it map
	- map relates one sequence to another. The type map relates keys to values. There is a deep symmetry between the two: maps are usually sparse, and the relationships between keys and values may be arbitrarily complex. The map function, on the other hand, usually expresses the same type of relationship, applied to a series of elements in fixed order.

- Building Sequences
	-  iterate - `(take 10 (iterate inc 0))`
		- `(take 10 (iterate (fn [x] (if (odd? x) (+ 1 x) (/ x 2))) 10))`
	-  `(take 10 (repeat :hi))`
	-  Range - `(range 0 100 5)`
	-  Cycle - `(take 10 (cycle [1 2 3]))`
	-  Iterate is handy when working with infinite sequences - repeat is it's partner in crime

- Transforming Sequences
	- Given a sequence, we often want to find a related sequence
	- 111Clojure (map (fn [n vehicle] (str "I've got " n " " vehicle "s"))
         [0 200 9]
         ["car" "train" "kiteboard"])
				 ``` = ("I've got 0 cars" "I've got 200 trains" "I've got 9 kiteboards")
	- interpose - `(interpose :and [1 2 3 4])`
	- reverse - `(reverse [1 2 3])`
	-	`(apply str (reverse "woolf"))`
	- seq - `(seq "sato")` -breaks things up
	- Shuffle - `(shuffle [1 2 3 4])`
	- `(apply str (shuffle (seq "abracadabra")))`
	-	`(frequencies [:meow :mrrrow :meow :meow])` = {:meow 3, :mrrrow 1}
	- After transforming a sequence, we often want to collapse it in some way; to derive some smaller value. For instance, we might want the number of times each element appears in a sequence:

- Subsequnces
	- `take`, selects the first n elements. `drop` removes the first n elements.
	- can also use take-last / drop-last to get the last items
	- Can do take positives / split at certain point
	- After transforming a sequence, we often want to collapse it in some way; to derive some smaller value. For instance, we might want the number of times each element appears in a sequence:

This is all very similar to Excel just with some name changes - functions such as filer, take, drop, seq, frequency - just need to learn the name and will be good to go.

## Chapter 6

Go from immutable references to complex concurrent transactions.

- Immutability 
    - let bindings and function arguments are immutable: they never change
    - The expression (inc x) did not alter x: x remained 1. The same applies to strings, lists, vectors, maps, sets, and most everything else in Clojure
    - Immutability also extends to let bindings, function arguments, and other symbols. Functions remember the values of those symbols at the time the function was constructed.

- Delays
    - Delays defer evaluation
    - (def later  ) allows you to set tu the function only once later is called.
    - This allows you do run expressions outside their sequential order
    - Delay creates a special function
    - (def later (delay (prn "Adding") (+ 1 2)))
    - Shortcut for deref = @

- Futures
    - futures parallelize evaluation
    - don’t need the result of evaluating these expressions yet, but I’d like it later
    - we can deref a future as many times as we want, and the expressions are only evaluated once
    - `(def x (future (prn "hi") (+ 1 2)))`

- Promises
    - Pending value
    - Like delays and futures, there’s no going back on our promises. Once delivered, a promise always refers to the same value.

- Vars
    - Vars can be read, set, and dynamically bound–but they aren’t easy to evolve
    - Using mutable vars allows us to write programs which we can redefine as we go along
    - ^:dynamic tells Clojure that this var can be overridden in one particular scope

- Atoms
    - The initial value of this atom is #{}. Unlike vars, atoms are not transparent. When evaluated, they don’t return their underlying values–but notice that when printed, the current value is hiding inside. To get the current value out of an atom, we have to use deref or @

- Refs
    - Atoms are a great way to represent state, but they are only linearizable individually
    - For multi-identity updates, we need a stronger safety property than single-atom linearizability. We want serializability: a global order. For this, Clojure has an identity type called a Ref.

```Clojure
user=> (def x (ref 0))
user=> (def y (ref 0))
user=> (dosync
         (ref-set x 1)
         (ref-set y 2))
2
user=> [@x @y]
[1 2]
```

## Chapter 7 

Interesting chapter with an overview of how Clojure structures a project and how namespaces work, as well as an introduction into reviewing a JSON data file and extracng information from it.

- Project Structure
  - When creating a new lein project a few files and folders are created:
  - project.clj defines the project: its name, its version, dependencies, and so on
  -  README.md, first file most people open when looking at a project. Lein generates a generic readme which can be filled in
  -  `doc` directory is for documentation; hand-written or automatically generated from the source code.
  -  `resources` is for files like images etc.
  -  `src` is where Clojure code lives,
  -  `test` contains the corresponding tests.
  -  `target` is where Leiningen stores compiled code, built packages, and so on.

- Namespace
  -  Every lein project starts out with a stub namespace containing a simple function
  -  The ns macro lets the Clojure compiler know that all following code belongs in the "name".core namespace
  -  As projects expand, we can add new namespaces to separate our work
  -  `def`, `defn`, and peers always work in the scope of a particular namespace
  -  To access things from other namespaces, we have to require them in the namespace definition `(ns user (:require [scratch.core]))`
  -  If using a var from another namespace often,  refer it to the local namespace–which means you may omit the namespace qualifier entirely `(ns user (:require [scratch.core :refer [foo]]))`

- Code and tests
  -  Wherever possible, we want to automate software tests–making the test itself another program
  -  A **failure **is when a test returns the wrong value. An **error **is when a test throws an exception

- Exploring data
  -  We can use libraries to parse data, solve mathematical problems, render graphics, perform simulations, talk to robots, or predict the weather
  -  To get a file for eg.JSON
    -  Add dependency `[cheshire "5.3.1"]`
```Clojure 
    (use 'cheshire.core)
(parse-string (slurp "2008.json"))
(first (parse-string (slurp "2008.json")))
(-> "2008.json" slurp parse-string first)
(def data (parse-string (slurp "2008.json") true))
```
  -  Can then do `(->> data (map :driving_under_influence) frequencies)`, `(->> data (map :driving_under_influence) frequencies (sort-by key) pprint)`
  -  `(->> data (sort-by :driving_under_influence) (take-last 10) (map #(select-keys % [:driving_under_influence :fips_county_code :fips_state_code])) pprint)`
  -  and many many more

