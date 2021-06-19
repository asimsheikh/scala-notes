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

