# scala-samples

1. Everything is an object; No primitives; Literals are also objects
2. Functional Lang
	i) Pure - aren't associated with objects and work without side effects
	ii) Higher Order - functions as argument or return 

3. Scala REPL

- Intermediate results are stored in res0 variable and res1 and so on.

4. Scala SBT

- Similar like Ant. Simple Build Tool

5. Scala Variables

- def - defines an immutable label for the right side content which is lazily evaluated - evaluate by name.

- val - defines an immutable label for the right side content which is eagerly/immediately evaluated - evaluated by value.

- var - defines a mutable variable, initially set to the evaluated right side content.

Example, def

```
scala> def something = 2 + 3 * 4 
something: Int
scala> something  // now it's evaluated, lazily upon usage
res30: Int = 14
```
Example, val

```
scala> val somethingelse = 2 + 3 * 5 // it's evaluated, eagerly upon definition
somethingelse: Int = 17
```
Example, var

```
scala> var aVariable = 2 * 3
aVariable: Int = 6

scala> aVariable = 5
aVariable: Int = 5
```
According to above, labels from def and val cannot be reassigned, and in case of any attempt an error like the below one will be raised:

```
scala> something = 5 * 6
<console>:8: error: value something_= is not a member of object $iw
       something = 5 * 6
       ^
```
When the class is defined like:

```
scala> class Person(val name: String, var age: Int)
defined class Person
```
and then instantiated with:

```
scala> def personA = new Person("Tim", 25)
personA: Person
```
an immutable label is created for that specific instance of Person (i.e. 'personA'). Whenever the mutable field 'age' needs to be modified, such attempt fails:

```
scala> personA.age = 44
personA.age: Int = 25
```
doesn't succeed but no error. 

6. Arithmetic operators are functions 

```
scala>age.*(5) //works
```

7. Infix notation support

- means that when a method takes 0 or 1 argument you can drop the . and ()
- this is why age.*(5) can be expressed as age * 5
- operator overloading works

8. Can use any Java class from Scala

9. Scala's class hierarchy

scala.Any 
https://www.scala-lang.org/api/2.12.5/scala/Any.html

scala.AnyVal 
- super type of all value types (all primitive like types; these also stay on heap in scala)
- there are 9 value types
- Unit is a special type ~ Java's void

```
val unit: Unit = ()			
```
scala.AnyRef 
- super tupe for all references (everything else)
- is an alias for Java's Object class
- `==` is similar to `equals` in scala for object reference comparison use `eq`

scala.Null
- all scala.AnyRef supertype

scala.Nothing
- all are super types to this - basically Any

10. Scala classes

- all fields are generated as private
- if val is used public getter is created but not setter
- if var is used public getter and setter are created
- if neither var nor val is used then the variable can be used only in the context of the constructor
- adding private to val or var makes the generated methods private

```
class Student(val name:String, val id: Int){
}
```
name and id are private

11. Scala constructors

- to add additional constructors use 

```
def this() {
//make call to parent constructor/default - just like in java
}
```

12. Singleton 

```
object Logger {
}
```
creates a singleton class and object.

Notice that def main is always in an object definition - it's how scala replicates java's static public main method

13. Companion Object

- if there is a class and object with same name

```
class Customer { }
object Customer { }
```
- all state within singleton are public static 
- companion objects are used to track singleton objects 

14. Subtype inheritance

- extends 

15. Anonymous subtype 
