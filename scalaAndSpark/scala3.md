# Scala Programming

## Flow Control

### If-Else examples

```scala
val person = "George"

if(person == "Sammy"){
    println("Welcome Sammy!")
}else if(person =="George"){
    println("Welcome George!")
}else{
    println("Welcome, what's your name?")
}
```

### Logical Operators

```scala
// AND &&
println((1 == 2) && (2 == 2)) // false
println((1 == 1) && (2 == 2)) // true
// OR ||
println((1 == 2) || (2 == 2)) // true
println((1 == 1) || (2 == 2)) // true
// NOT !
println(!(1==1)) // false
println(!(2==1)) // true
```

## For Loops

### General Format

```scala
//  for(item <- iterable_sequence){
//    do something
//  }
```

### Lists & Range

```scala
for(item <- List("a","b","c")){
  println(item)
}

// Range
for(num <- Range(0,3)){
  println(num)
}

for(anything <- Range(0,3)){
  println("hello")
}


// Building it up with Flow Control!
for(num <- Range(0,10)){
  if(num % 2 == 0){
    println(s"$num is even")
  }else{
    println(s"$num is odd")
  }
}

// One more example
val names = List("John","Abe","Cindy","Cat")

for(name <- names){
  if(name.startsWith("C")){
    println("$name starts with a C")
  }
}
```

## While Loop

### Examples

```scala
// Needs to be var, we will reassign
var x = 0

while(x < 5){
  println(s"x is currently $x")
  println("x is still less than 5, adding 1 to x")
  x = x+1
}
```

### Break

* Scala doesn't have built-in break functionality
* Allows you to break out of a loop based on some condition

```scala 
import util.control.Breaks._

var y = 0

while(y < 10){
  println(s"y is currently $y")
  println("y is still less than 10, adding 1 to y")
  y = y+1
  if(y == 3) break
}
```

## Functions

* Functions allow you to easily re-use and call code segments!

### General Format

```scala
// def functionName(input1:type,intput2:type): return type = {
//     do stuff
// }
```

### Examples

```scala
def simple(): Unit = {
  println("Simple Print")
}
simple()

// Adding two inputs
def adder(num1:Int,num2:Int): Int = {
  return num1 + num2
}

val x = adder(2,3)
println(x)

// Greeting Someone
def greetName(name:String): String = {
  return s"Hello $name"
}
val fullgreet = greetName("Jose")
println(fullgreet)

// Check if a number is prime
def isPrime(numcheck:Int): Boolean = {
  for(n <- Range(2,numcheck)){
    if(numcheck%n == 0){
      return false
    }
    }
    return true
}


println(isPrime(10))
println(isPrime(23))
```

### Using Collections

```scala
val numbers = List(1,2,3,7)
def check(nums:List[Int]): List[Int]={
  return nums
}

println(check(numbers))

// "One Line Functions"
def quickgreet(name:String) = s"Hello $name"
println(quickgreet("Sammy"))
```