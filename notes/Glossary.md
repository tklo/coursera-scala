# Scala Glossary

## A

algebraic data type
A type defined by providing several alternatives, each of which comes with its own constructor. It usually comes with a way to decompose the type through pattern matching. The concept is found in specification languages and functional programming languages. Algebraic data types can be emulated in Scala with case classes.

alternative (case)
A branch of a match expression. It has the form “case pattern => expression.”

annotation
An annotation appears in source code and is attached to some part of the syntax. Annotations are computer processable, so you can use them to effectively add an extension to Scala.

anonymous class
An anonymous class is a synthetic subclass generated by the Scala compiler from a new expression in which the class or trait name is followed by curly braces. The curly braces contains the body of the anonymous subclass, which may be empty. However, if the name following new refers to a trait or class that contains abstract members, these must be made concrete inside the curly braces that define the body of the anonymous subclass.

anonymous function
Another name for function literal.

apply
You can apply a method, function, or closure to arguments, which means you invoke it on those arguments.

argument
When a function is invoked, an argument is passed for each parameter of that function. The parameter is the variable that refers to the argument. The argument is the object passed at invocation time. In addition, applications can take (command line) arguments that show up in the Array[String] passed to main methods of singleton objects.

assign
You can assign an object to a variable. Afterwards, the variable will refer to the object.

auxiliary constructor
Extra constructors defined inside the curly braces of the class definition, which look like method definitions named this, but with no result type.

block
One or more expressions and declarations surrounded by curly braces. When the block evaluates, all of its expressions and declarations are processed in order, and then the block returns the value of the last expression as its own value. Blocks are commonly used as the bodies of functions, for expressions, while loops, and any other place where you want to group a number of statements together. More formally, a block is an encapsulation construct for which you can only see side effects and a result value. The curly braces in which you define a class or object do not, therefore, form a block, because fields and methods (which are defined inside those curly braces) are visible from the out- side. Such curly braces form a template.

bound variable
A bound variable of an expression is a variable that’s both used and defined inside the expression. For instance, in the function literal expression (x: Int) => (x, y), both variables x and y are used, but only x is bound, because it is defined in the expression as an Int and the sole argument to the function described by the expression.

by-name parameter
A parameter that is marked with a => in front of the parameter type, e.g., (x: => Int). The argument corresponding to a by-name parameter is evaluated not before the method is invoked, but each time the parameter is referenced by name inside the method. If a parameter is not by-name, it is by-value.

by-value parameter
A parameter that is not marked with a => in front of the parameter type, e.g., (x: Int). The argument corresponding to a by-value parameter is evaluated before the method is invoked. By-value parameters contrast with by-name parameters.

class
Defined with the class keyword, a class may either be abstract or concrete, and may be parameterized with types and values when instantiated. In new Array[String](2), the class being instantiated is Array and the type of the value that results is Array[String]. A class that takes type parameters is called a type constructor. A type can be said to have a class as well, as in: the class of type Array[String] is Array.

closure
A function object that captures free variables, and is said to be “closed” over the variables visible at the time it is created.

companion class
A class that shares the same name with a singleton object defined in the same source file. The class is the singleton object’s companion class.

companion object
A singleton object that shares the same name with a class defined in the same source file. Companion objects and classes have access to each other’s private members. In addition, any implicit conversions defined in the companion object will be in scope anywhere the class is used.

contravariant
A contravariant annotation can be applied to a type parameter of a class or trait by putting a minus sign (-) before the type parameter. The class or trait then subtypes contravariantly with—in the opposite direction as—the type annotated parameter. For example, Function1 is contravariant in its first type parameter, and so Function1[Any, Any] is a subtype of Function1[String, Any].

covariant
A covariant annotation can be applied to a type parameter of a class or trait by putting a plus sign (+) before the type parameter. The class or trait then subtypes covariantly with—in the same direction as—the type annotated parameter. For example, List is covariant in its type parameter, so List[String] is a subtype of List[Any].

currying
A way to write functions with multiple parameter lists. For instance def f(x: Int)(y: Int) is a curried function with two parameter lists. A curried function is applied by passing several arguments lists, as in: f(3)(4). However, it is also possible to write a partial application of a curried function, such as f(3).

declare
You can declare an abstract field, method, or type, which gives an entity a name but not an implementation. The key difference between declarations and definitions is that definitions establish an implementation for the named entity, declarations do not.

define
To define something in a Scala program is to give it a name and an implementation. You can define classes, traits, singleton objects, fields, methods, local functions, local variables, etc. Because definitions always involve some kind of implementation, abstract members are declared not defined.

direct subclass
A class is a direct subclass of its direct superclass.

direct superclass
The class from which a class or trait is immediately derived, the nearest class above it in its inheritance hierarchy. If a class Parent is mentioned in a class Child’s optional extends clause, then Parent is the direct superclass of Child. If a trait is mentioned in Child’s extends clause, the trait’s direct superclass is the Child’s direct superclass. If Child has no extends clause, then AnyRef is the direct superclass of Child. If a class’s direct superclass takes type parameters, for example class Child extends Parent[String], the direct superclass of Child is still Parent, not Parent[String]. On the other hand, Parent[String] would be the direct supertype of Child. See supertype for more discussion of the distinction between class and type.

equality
When used without qualification, equality is the relation between values expressed by ==. See also reference equality.

existential type
An existential type includes references to type variables that are unknown. For example, Array[T] forSome { type T } is an existential type. It is an array of T, where T is some completely unknown type. All that is assumed about T is that it exists at all. This assumption is weak, but it means at least that an Array[T] forSome { type T } is indeed an array and not a banana.

expression
Any bit of Scala code that yields a result. You can also say that an expression evaluates to a result or results in a value.

filter
An if followed by a boolean expression in a for expression. In for(i <- 1 to 10; if i % 2 == 0), the filter is “if i % 2 == 0”. The value to the right of the if is the filter expression. Also known as a guard.

filter expression
A filter expression is the boolean expression following an if in a for expression. In for( i <- 1 to 10 ; if i % 2 == 0),the filter expression is “i % 2 == 0”.

first-class function
Scala supports first-class functions, which means you can express functions in function literal syntax, i.e., (x: Int) => x + 1, and that functions can be represented by objects, which are called function values.

for comprehension
A for comprehension is a type of for expression that creates a new collection. For each iteration of the for comprehension, the yield clause defines an element of the new collection. For example, for (i <- (0 until 2); j <- (2 until 4)) yield (i, j) returns the collection Vector((0,2), (0,3), (1,2), (1,3)).

for expression
A for expression is either a for loop, which iterates over one or more collections, or a for comprehension, which builds a new collection from the elements of one or more collections. A for expression is built up of generators, filters, variable definitions, and (in the case of for comprehensions) a yield clause.

for loop
A for loop is a type of for expression that loops over one or more collections. Since for loops return unit, they usually produce side-effects. For example, for (i <- 0 until 100) println(i) prints the numbers 0 through 99.

free variable
A free variable of an expression is a variable that’s used inside the expression but not defined inside the expression. For instance, in the function literal expression (x: Int) => (x, y), both variables x and y are used, but only y is a free variable, because it is not defined inside the expression.

function
A function can be invoked with a list of arguments to produce a result. A function has a parameter list, a body, and a result type. Functions that are members of a class, trait, or singleton object are called methods. Functions defined inside other functions are called local functions. Functions with the result type of Unit are called procedures. Anonymous functions in source code are called function literals. At run time, function literals are instantiated into objects called function values.

function literal
A function with no name in Scala source code, specified with function literal syntax. For example, (x: Int, y: Int) => x + y.

function value
A function object that can be invoked just like any other function. A function value’s class extends one of the FunctionN traits (e.g., Function0, Function1) from package scala, and is usually expressed in source code via function literal syntax. A function value is “invoked” when its apply method is called. A function value that captures free variables is a closure.

functional style
The functional style of programming emphasizes functions and evaluation results and deemphasizes the order in which operations occur. The style is characterized by passing function values into looping methods, immutable data, methods with no side effects. It is the dominant paradigm of languages such as Haskell and Erlang, and contrasts with the imperative style.

generator
A generator defines a named val and assigns to it a series of values in a for expression. For example, in for(i <- 1 to 10), the generator is “i <- 1 to 10”. The value to the right of the <- is the generator expression.

generator expression
A generator expression generates a series of values in a for expression. For example, in for(i <- 1 to 10), the generator expression is “1 to 10”.

generic class
A class that takes type parameters. For example, because scala.List takes a type parameter, scala.List is a generic class.

generic trait
A trait that takes type parameters. For example, because trait scala.collection.Set takes a type parameter, it is a generic trait.

guard
See filter.

helper function
A function whose purpose is to provide a service to one or more other functions nearby. Helper functions are often implemented as local functions.

helper method
A helper function that’s a member of a class. Helper methods are often private.

immutable
An object is immutable if its value cannot be changed after it is created in any way visible to clients. Objects may or may not be immutable.

imperative style
The imperative style of programming emphasizes careful sequencing of operations so that their effects happen in the right order. The style is characterized by iteration with loops, mutating data in place, and methods with side effects. It is the dominant paradigm of languages such as C, C++, C# and Java, and contrasts with the functional style.

initialize
When a variable is defined in Scala source code, you must initialize it with an object.

instance
An instance, or class instance, is an object, a concept that exists only at run time.

instantiate
To instantiate a class is to make a new object from the class, an action that happens only at run time.

invariant
Invariant is used in two ways. It can mean a property that always holds true when a data structure is well-formed. For example, it is an invariant of a sorted binary tree that each node is ordered before its right subnode, if it has a right subnode. Invariant is also sometimes used as a synonym for nonvariant: “class Array is invariant in its type parameter.”

invoke
You can invoke a method, function, or closure on arguments, meaning its body will be executed with the specified arguments.

JVM
The JVM is the Java Virtual Machine, or runtime, that hosts a running Scala program.

literal
1, "One", and (x: Int) => x + 1 are examples of literals. A literal is a shorthand way to describe an object, where the shorthand exactly mirrors the structure of the created object.

local function
A local function is a def defined inside a block. To contrast, a def defined as a member of a class, trait, or singleton object is called a method.

local variable
A local variable is a val or var defined inside a block. Although similar to local variables, parameters to functions are not referred to as local variables, but simply as parameters or “variables” without the “local.”

member
A member is any named element of the template of a class, trait, or singleton object. A member may be accessed with the name of its owner, a dot, and its simple name. For example, top-level fields and methods defined in a class are members of that class. A trait defined inside a class is a member of its enclosing class. A type defined with the type keyword in a class is a member of that class. A class is a member of the package in which is it defined. By contrast, a local variable or local function is not a member of its surrounding block.

message
Actors communicate with each other by sending each other messages. Sending a message does not interrupt what the receiver is doing. The receiver can wait until it has finished its current activity and its invariants have been reestablished.

meta-programming
Meta-programming software is software whose input is itself software. Compilers are meta-programs, as are tools like scaladoc. Meta-programming software is required in order to do anything with an annotation.

method
A method is a function that is a member of some class, trait, or singleton object.

mixin
Mixin is what a trait is called when it is being used in a mixin composition. In other words, in “trait Hat,” Hat is just a trait, but in “new Cat extends AnyRef with Hat,” Hat can be called a mixin. When used as a verb, “mix in” is two words. For example, you can mix traits _in_to classes or other traits.

mixin composition
The process of mixing traits into classes or other traits. Mixin composition differs from traditional multiple inheritance in that the type of the super reference is not known at the point the trait is defined, but rather is determined anew each time the trait is mixed into a class or other trait.

modifier
A keyword that qualifies a class, trait, field, or method definition in some way. For example, the private modifier indicates that a class, trait, field, or method being defined is private.

multiple definitions
The same expression can be assigned in multiple definitions if you use the syntax val v1, v2, v3 = exp.

nonvariant
A type parameter of a class or trait is by default nonvariant. The class or trait then does not subtype when that parameter changes. For example, because class Array is nonvariant in its type parameter, Array[String] is neither a subtype nor a supertype of Array[Any].

operation
In Scala, every operation is a method call. Methods may be invoked in operator notation, such as b + 2, and when in that notation, + is an operator.

parameter
Functions may take zero to many parameters. Each parameter has a name and a type. The distinction between parameters and arguments is that arguments refer to the actual objects passed when a function is invoked. Parameters are the variables that refer to those passed arguments.

parameterless function
A function that takes no parameters, which is de- fined without any empty parentheses. Invocations of parameterless functions may not supply parentheses. This supports the uniform access principle, which enables the def to be changed into a val without requiring a change to client code.

parameterless method
A parameterless method is a parameterless function that is a member of a class, trait, or singleton object.

parametric field
A field defined as a class parameter.

partially applied function
A function that’s used in an expression and that misses some of its arguments. For instance, if function f has type Int => Int => Int, then f and f(1) are partially applied functions.

path-dependent type
A type like swiss.cow.Food. The swiss.cow part is a path that forms a reference to an object. The meaning of the type is sensitive to the path you use to access it. The types swiss.cow.Food and fish.Food, for example, are different types.

pattern
In a match expression alternative, a pattern follows each case keyword and precedes either a pattern guard or the => symbol.

pattern guard
In a match expression alternative, a pattern guard can follow a pattern. For example, in “case x if x % 2 == 0 => x + 1”, the pattern guard is “if x % 2 == 0”. A case with a pattern guard will only be selected if the pattern matches and the pattern guard yields true.

predicate
A predicate is a function with a Boolean result type.

primary constructor
The main constructor of a class, which invokes a superclass constructor, if necessary, initializes fields to passed values, and executes any top-level code defined between the curly braces of the class. Fields are initialized only for value parameters not passed to the superclass constructor, except for any that are not used in the body of the class and can therefore be optimized away.

procedure
A procedure is a function with result type of Unit, which is therefore executed solely for its side effects.

reassignable
A variable may or may not be reassignable. A var is reassignable while a val is not.

recursive
A function is recursive if it calls itself. If the only place the function calls itself is the last expression of the function, then the function is tail recursive.

reference
A reference is the Java abstraction of a pointer, which uniquely identifies an object that resides on the JVM’s heap. Reference type variables hold references to objects, because reference types (instances of AnyRef) are implemented as Java objects that reside on the JVM’s heap. Value type variables, by contrast, may sometimes hold a reference (to a boxed wrapper type) and sometimes not (when the object is being represented as a primitive value). Speaking generally, a Scala variable refers to an object. The term “refers” is more abstract than “holds a reference.” If a variable of type scala.Int is currently represented as a primitive Java int value, then that variable still refers to the Int object, but no reference is involved.

reference equality
Reference equality means that two references identify the very same Java object. Reference equality can be determined, for reference types only, by calling eq in AnyRef. (In Java programs, reference equality can be determined using == on Java reference types.)

reference type
A reference type is a subclass of AnyRef. Instances of reference types always reside on the JVM’s heap at run time.

referential transparency
A property of functions that are independent of temporal context and have no side effects. For a particular input, an invocation of a referentially transparent function can be replaced by its result without changing the program semantics.

refers
A variable in a running Scala program always refers to some object. Even if that variable is assigned to null, it conceptually refers to the Null object. At runtime, an object may be implemented by a Java object or a value of a primitive type, but Scala allows programmers to think at a higher level of abstraction about their code as they imagine it running. See also reference.

refinement type
A type formed by supplying a base type a number of members inside curly braces. The members in the curly braces refine the types that are present in the base type. For example, the type of “animal that eats grass” is Animal { type SuitableFood = Grass }.

result
An expression in a Scala program yields a result. The result of every expression in Scala is an object.

result type
A method’s result type is the type of the value that results from calling the method. (In Java, this concept is called the return type.)

return
A function in a Scala program returns a value. You can call this value the result of the function. You can also say the function results in the value. The result of every function in Scala is an object.

runtime
The Java Virtual Machine, or JVM, that hosts a running Scala program. Runtime encompasses both the virtual machine, as defined by the Java Virtual Machine Specification, and the runtime libraries of the Java API and the standard Scala API. The phrase at run time (with a space between run and time) means when the program is running, and contrasts with compile time.

runtime type
The type of an object at run time. To contrast, a static type is the type of an expression at compile time. Most runtime types are simply bare classes with no type parameters. For example, the runtime type of "Hi" is String, and the runtime type of (x: Int) => x + 1 is Function1. Runtime types can be tested with isInstanceOf.

script
A file containing top level definitions and statements, which can be run directly with scala without explicitly compiling. A script must end in an expression, not a definition.

selector
The value being matched on in a match expression. For example, in “s match { case _ => }”, the selector is s.

self type
A self type of a trait is the assumed type of this, the receiver, to be used within the trait. Any concrete class that mixes in the trait must ensure that its type conforms to the trait’s self type. The most common use of self types is for dividing a large class into several traits (as described in Chapter 29 of Programming in Scala.

semi-structured data
XML data is semi-structured. It is more structured than a flat binary file or text file, but it does not have the full structure of a programming language’s data structures.

serialization
You can serialize an object into a byte stream which can then be saved to files or transmitted over the network. You can later deserialize the byte stream, even on different computer, and obtain an object that is the same as the original serialized object.

shadow
A new declaration of a local variable shadows one of the same name in an enclosing scope.

signature
Signature is short for type signature.

singleton object
An object defined with the object keyword. Each singleton object has one and only one instance. A singleton object that shares its name with a class, and is defined in the same source file as that class, is that class’s companion object. The class is its companion class. A singleton object that doesn’t have a companion class is a standalone object.

standalone object
A singleton object that has no companion class.

statement
An expression, definition, or import, i.e., things that can go into a template or a block in Scala source code.

static type
See type.

structural type
A refinement type where the refinements are for members not in the base type. For example, { def close(): Unit } is a structural type, because the base type is AnyRef, and AnyRef does not have a member named close.

subclass
A class is a subclass of all of its superclasses and supertraits.

subtrait
A trait is a subtrait of all of its supertraits.

subtype
The Scala compiler will allow any of a type’s subtypes to be used as a substitute wherever that type is required. For classes and traits that take no type parameters, the subtype relationship mirrors the subclass relationship. For example, if class Cat is a subclass of abstract class Animal, and neither takes type parameters, type Cat is a subtype of type Animal. Likewise, if trait Apple is a subtrait of trait Fruit, and neither takes type parameters, type Apple is a subtype of type Fruit. For classes and traits that take type parameters, however, variance comes into play. For example, because abstract class List is declared to be covariant in its lone type parameter (i.e., List is declared List[+A]), List[Cat] is a subtype of List[Animal], and List[Apple] a subtype of List[Fruit]. These subtype relationships exist even though the class of each of these types is List. By contrast, because Set is not declared to be covariant in its type parameter (i.e., Set is declared Set[A] with no plus sign), Set[Cat] is not a subtype of Set[Animal]. A subtype should correctly implement the contracts of its supertypes, so that the Liskov Substitution Principle applies, but the compiler only verifies this property at the level of type checking.

superclass
A class’s superclasses include its direct superclass, its direct superclass’s direct superclass, and so on, all the way up to Any.

supertrait
A class’s or trait’s supertraits, if any, include all traits directly mixed into the class or trait or any of its superclasses, plus any supertraits of those traits.

supertype
A type is a supertype of all of its subtypes.

synthetic class
A synthetic class is generated automatically by the compiler rather than being written by hand by the programmer.

tail recursive
A function is tail recursive if the only place the function calls itself is the last operation of the function.

target typing
Target typing is a form of type inference that takes into account the type that’s expected. In nums.filter((x) => x > 0), for example, the Scala compiler infers type of x to be the element type of nums, because the filter method invokes the function on each element of nums.

template
A template is the body of a class, trait, or singleton object definition. It defines the type signature, behavior and initial state of the class, trait, or object.

trait
A trait, which is defined with the trait keyword, is like an abstract class that cannot take any value parameters and can be “mixed into” classes or other traits via the process known as mixin composition. When a trait is being mixed into a class or trait, it is called a mixin. A trait may be parameterized with one or more types. When parameterized with types, the trait constructs a type. For example, Set is a trait that takes a single type parameter, whereas Set[Int] is a type. Also, Set is said to be “the trait of” type Set[Int].

type
Every variable and expression in a Scala program has a type that is known at compile time. A type restricts the possible values to which a variable can refer, or an expression can produce, at run time. A variable or expression’s type can also be referred to as a static type if necessary to differentiate it from an object’s runtime type. In other words, “type” by itself means static type. Type is distinct from class because a class that takes type parameters can construct many types. For example, List is a class, but not a type. List[T] is a type with a free type parameter. List[Int] and List[String] are also types (called ground types because they have no free type parameters). A type can have a “class” or “trait.” For example, the class of type List[Int] is List. The trait of type Set[String] is Set.

type constraint
Some annotations are type constraints, meaning that they add additional limits, or constraints, on what values the type includes. For example, @positive could be a type constraint on the type Int, limiting the type of 32-bit integers down to those that are positive. Type constraints are not checked by the standard Scala compiler, but must instead be checked by an extra tool or by a compiler plugin.

type constructor
A class or trait that takes type parameters.

type parameter
A parameter to a generic class or generic method that must be filled in by a type. For example, class List is defined as “class List[T] { . . . ”, and method identity, a member of object Predef, is defined as “def identity[T](x:T) = x”. The T in both cases is a type parameter.

type signature
A method’s type signature comprises its name, the number, order, and types of its parameters, if any, and its result type. The type signature of a class, trait, or singleton object comprises its name, the type signatures of all of its members and constructors, and its declared inheritance and mixin relations.

uniform access principle
The uniform access principle states that variables and parameterless functions should be accessed using the same syntax. Scala supports this principle by not allowing parentheses to be placed at call sites of parameterless functions. As a result, a parameterless function definition can be changed to a val, or vice versa, without affecting client code.

unreachable
At the Scala level, objects can become unreachable, at which point the memory they occupy may be reclaimed by the runtime. Unreachable does not necessarily mean unreferenced. Reference types (instances of AnyRef) are implemented as objects that reside on the JVM’s heap. When an instance of a reference type becomes unreachable, it indeed becomes unreferenced, and is available for garbage collection. Value types (instances of AnyVal) are implemented as both primitive type values and as instances of Java wrapper types (such as java.lang.Integer), which reside on the heap. Value type instances can be boxed (converted from a primitive value to a wrapper object) and unboxed (converted from a wrapper object to a primitive value) throughout the lifetime of the variables that refer to them. If a value type instance currently represented as a wrapper object on the JVM’s heap becomes unreachable, it indeed becomes unreferenced, and is available for garbage collection. But if a value type currently represented as a primitive value becomes unreachable, then it does not become unreferenced, because it does not exist as an object on the JVM’s heap at that point in time. The runtime may reclaim memory occupied by unreachable objects, but if an Int, for example, is implemented at run time by a primitive Java int that occupies some memory in the stack frame of an executing method, then the memory for that object is “reclaimed” when the stack frame is popped as the method completes. Memory for reference types, such as Strings, may be reclaimed by the JVM’s garbage collector after they become unreachable.

unreferenced
See unreachable.

value
The result of any computation or expression in Scala is a value, and in Scala, every value is an object. The term value essentially means the image of an object in memory (on the JVM’s heap or stack).

value type
A value type is any subclass of AnyVal, such as Int, Double, or Unit. This term has meaning at the level of Scala source code. At runtime, instances of value types that correspond to Java primitive types may be implemented in terms of primitive type values or instances of wrapper types, such as java.lang.Integer. Over the lifetime of a value type instance, the runtime may transform it back and forth be- tween primitive and wrapper types (i.e., to box and unbox it).

variable
A named entity that refers to an object. A variable is either a val or a var. Both vals and vars must be initialized when defined, but only vars can be later reassigned to refer to a different object.

variance
A type parameter of a class or trait can be marked with a variance annotation, either covariant (+) or contravariant (-). Such variance annotations indicate how subtyping works for a generic class or trait. For example, the generic class List is covariant in its type parameter, and thus List[String] is a subtype of List[Any]. By default, i.e., absent a + or - annotation, type parameters are nonvariant.

yield
An expression can yield a result. The yield keyword designates the result of a for comprehension.
