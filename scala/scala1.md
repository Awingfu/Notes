# Scala

## Values vs Variables

```scala
val a: Int = 4
var b: Double = 4
```

* Values are not mutable and cannot be reassigned, whereas variables can be.
* Typecasting not needed.
  * Will automatically cast on assignment, but you have to assign on initialization

## Booleans and Comparisons

* Use '==', '!=', '>=', '<=', '>', '<'
* 'Boolean' type

## Strings & Regex

### Interpolate strings

```scala
val name = "Adam"
val greet = s"Hello ${name}"
val greet1 = s"Hello $name"
val greet2 = f"Hello $name"
// all return 'Hello Adam'
```

### Printing to console

```scala
val greet = "Hello World"
println(greet)
//returns 'Hello World'
printf("A string $s, an integer %d, a float $f","Hi",10,2.5)
//returns 'A string Hi, an integer 10, a fload 2.5'
printf("A float %1.2f", 1.2395)
//returns 'A float 1.24'
```

### Regex

* Typing '.' after a variable and clicking enter/return will return a list of available functions

```scala
val st = "This is a long string"
st.charAt(0)
//returns 'Char = T'
st.indexOf("a")
//returns 'Int = 8'
st slice (0,4)
//returns 'String = This'
st matches "This is a long string"
//returns 'Boolean = true'
st matches "This"
//returns 'Boolean = false'
st contains "long"
//returns 'Boolean = true'
```

## Tuples

```scala
(1,2.3,"Adam")
//retrns '(Int, Double, String) = (1,2.3,Adam)'
val nestedTup = (1.2,3,(2,4))
//returns '(Double, Int, (Int, Int)) = (1.2,3,(2,4))'
//indexes start at 1
nestedTup._2
//returns 'Int = 3'
nestedTup._3._2
//returns 'Int = 4'


```