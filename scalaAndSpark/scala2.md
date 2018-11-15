# Scala Collection Methods

## Lists

* Lists are an immutable sequence of elements (singly linked list)

Basic List of Numbers

```scala
val evens = List(2,4,6,8,10,12)
List[Int] = List(2, 4, 6, 8, 10, 12)
```

Indexing Items (Starts at zero)

```scala
evens(0)
res0: Int = 2

evens(1)
res1: Int = 4
```

Head and Tail

```scala
evens.head
res3: Int = 2

evens.tail
res4: List[Int] = List(4, 6, 8, 10, 12)

evens
res5: List[Int] = List(2, 4, 6, 8, 10, 12)
```

### Element Types

```scala
//Any
val my_list = List("a",2,true)
my_list: List[Any] = List(a, 2, true)

// Nested
val my_list = List(List(1,2,3),List(4,5,6))
my_list: List[List[Int]] = List(List(1, 2, 3), List(4, 5, 6))

// Double and Int
val my_list = List(1,2,3.0)
my_list: List[Double] = List(1.0, 2.0, 3.0)

// List of Tuple Pairs
val my_list = List(("a",1),("b",2),("c",3))
my_list: List[(String, Int)] = List((a,1), (b,2), (c,3))
```

List Operations

```scala
val my_list = List(3,6,1,7,10)
my_list: List[Int] = List(3, 6, 1, 7, 10)

my_list.sorted
res7: List[Int] = List(1, 3, 6, 7, 10)

my_list.size
res8: Int = 5

my_list.max
res9: Int = 10

my_list.min
res39: Int = 1

my_list.sum
res40: Int = 27

my_list.product
res41: Int = 1260

// Using drop for slicing:
val x = List(1,2,3,4)
x: List[Int] = List(1, 2, 3, 4)

x.drop(2)
res3: List[Int] = List(3, 4)

x.takeRight(3)
res4: List[Int] = List(2, 3, 4)
// Use Tab to explore the other methods!
```

## Array

* Collection of variables
* [Difference between array and list](http://stackoverflow.com/questions/2712877/difference-between-array-and-list-in-scala)
  * Lists have better performance
  * Lists are immutable vs Arrays are mutable

### Examples

```scala
val arr = Array(1,2,3)
arr: Array[Int] = Array(1, 2, 3)

val arr = Array("a","b","c")
arr: Array[String] = Array(a, b, c)
```

### Range

```scala
// Use of range() method to generate an array containing
// a sequence of increasing integers in a given range.
Array.range(0,10)
res64: Array[Int] = Array(0, 1, 2, 3, 4, 5, 6, 7, 8, 9)

Array.range(0,10,2)
res65: Array[Int] = Array(0, 2, 4, 6, 8)

// Or just call Range with a capital R
Range(0,5)
res1: scala.collection.immutable.Range = Range(0, 1, 2, 3, 4)

Range(0,10,2)
res2: scala.collection.immutable.Range = Range(0, 2, 4, 6, 8)
```

## Sets

* Set is a collection that contains no duplicate elements.
* There are two kinds of Sets, the immutable and the mutable.

### Examples

```scala
val s = Set()
s: scala.collection.immutable.Set[Nothing] = Set()

val s = Set(1,2,3)
s: scala.collection.immutable.Set[Int] = Set(1, 2, 3)

val s = Set(1,1,2,2,2,3,3,3)
s: scala.collection.immutable.Set[Int] = Set(1, 2, 3)

// Mutable Sets
val s = collection.mutable.Set(1,2,3)
s: scala.collection.mutable.Set[Int] = Set(1, 2, 3)

s += 4
res50: s.type = Set(1, 2, 3, 4)

s
res51: scala.collection.mutable.Set[Int] = Set(1, 2, 3, 4)

s.add(5)
res52: Boolean = true

s
res53: scala.collection.mutable.Set[Int] = Set(1, 5, 2, 3, 4)
```

### Set Operations

```scala
s.max
res54: Int = 5

s.min
res55: Int = 1

// Cast to Set
val mylist = List(1,2,3,1,2,3)
mylist: List[Int] = List(1, 2, 3, 1, 2, 3)

mylist.toSet
res59: scala.collection.immutable.Set[Int] = Set(1, 2, 3)
```

## Maps

* (Key,Value) Pair Storage aka Hash Table or Dictionary

### Examples

```scala
val mymap = Map(("a",1),("b",2),("c",3))

mymap: scala.collection.immutable.Map[String,Int] = Map(a -> 1, b -> 2, c
 -> 3)

// Lookups
mymap("a")
res12: Int = 1

// Noneif not present
mymap get "b"
res15: Option[Int] = Some(2)

// Temp additions on immutable
mymap + ("z"->99)
res19: scala.collection.immutable.Map[String,Int] = Map(a -> 1, b -> 2, c
 -> 3, z -> 99)
```

### Mutable maps

```scala
val mymutmap = collection.mutable.Map(("x",1),("y",2),("z",3))
mymutmap: scala.collection.mutable.Map[String,Int] = Map(z -> 3, y -> 2,
x -> 1)

// Permanent Additions
mymutmap += ("new"->999)

res29: mymutmap.type = Map(z -> 3, y -> 2, x -> 1, new -> 999)

mymutmap
res30: scala.collection.mutable.Map[String,Int] = Map(z -> 3, y -> 2, x -
> 1, new -> 999)
```

### Useful methods

```scala
mymap.keys
res34: Iterable[String] = Set(a, b, c)

mymap.values
res35: Iterable[Int] = MapLike(1, 2, 3)
```