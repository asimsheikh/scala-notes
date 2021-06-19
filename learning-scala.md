Decided to learn Scala 3 after watching the Lex Fridman podcast with Charles
Hodgkinson.

### Installation

Firstly I installed the build tool for scala, through the sbt package. [sbt
download](https://www.scala-sbt.org/download.html).

### Introduction

sbt console

At the Scala repl 

```scala
val x: Int = 12
val y = 12.0
```

All values are immutable

```scala
x = 12

console>:12: error: reassignment to val
```

We can have scoped values, so they do not pollute the global scope. In the
example x and y are declared in the brackets for z, and the last expression is
the result of the block ie 300.

```scala
val x = 12
val y = 14

val z = {
   val x = 100
   val y = 200
   x + y
}
```
We can also create singleton objects that do not need to be newed up. In the
example we also demonstrate two versions of string interpolation, one that is
not type safe, and the f mode which is type safe.

```scala
object HelloWorld { 
  def main(args: Array[String]) {
    val name = "Asim"
    val age = 30
    println(s"$name is $age year's old")
    println(f"$name%s is $age%d year's old")
    println(s"Hello \nworld")
    println(raw"Hello \nworld")
  }
}

HelloWorld.main(Array(""))
```

### Comments 

Comments can be defined as follows
```scala
// val x = 12   -- a single line comment
/* val y = 12
   val name = "Asim"
*/
```

### Conditionals - if and while statements 
For conditionals we have if statements and if expressions. In the first we need
to create variable to store the result, in the if expression the result of the
if expression is assigned to a variable.

```scala
val x = 20

var res = ""
if (x == 20) {
  res = "x == 20"
} else {
  res = "x != 20"
}

println(res)

// versus the if expression

val res2 = if (x == 20) "x == 20" else "x != 20"
println(res)
```

while loops are also available 
```scala
var x = 0
while (x < 10) {
 println(s"x = $x")
 x = x + 1
}

var y = 0
do { 
 println(s"y = $y")
 y + = 1
} while (y < 10) 
```

### For loops 

The general example is 

 for ( var <- aRange ) 

```scala
for (i <- 1 to 5) {
  println("i is $i")
}

for (i <- 1 to 9; j <- 1 to 3) {
  println(s"i using until $i")
}

val lst = List("Asim", "Faizan", "Sheikh")

for (x <- lst) { 
  println(s"$x")
}

val result = for {i <- lst} yield { i * i }
```

### Match Expressions

Using match expressions we can do pattern matching, a super powerful construct

```scala
val age = 18 

age match { 
  case 20 => println(age)
  case 10 => println("We are young")
  case _ => 20
}

val result = age match {
  case 20 => 20
  case 10 => 10
  case 100 => 100
  case _ => 0
} 

println("result = $result")

val i = 10
i match {
  case 1 | 3 | 5 | 7 | 9 => println("odd")
  case 2 | 4 | 6 | 8 | 10 => println("even")
}
```

