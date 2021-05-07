# what is functional programming?
Functional programming is a programming paradigm — a style of building the structure and elements of computer programs — that treats computation as the evaluation of mathematical functions and avoids changing-state and mutable data 
# what is a pure function and how do we know if something is a pure function?
The first fundamental concept we learn when we want to understand functional programming is pure functionsIt returns the same result if given the same arguments (it is also referred as deterministic)
It does not cause any observable side effects
# what are the benefits of a pure function?
The code’s definitely easier to test. We don’t need to mock anything. So we can unit test pure functions with different contexts:
Given a parameter A → expect the function to return value B
Given a parameter C → expect the function to return value D
A simple example would be a function to receive a collection of numbers and expect it to increment each element of this collection.
# what is immutability?
When data is immutable, its state cannot change after it’s created. If you want to change an immutable object, you can’t. Instead, you create a new object with the new value.
# what is Referential transparency?
Basically, if a function consistently yields the same result for the same input, it is referentially transparent.
pure functions + immutable data = referential transparency
# module:

# what is a module?
A Java module is a packaging mechanism that enables you to package a Java application or Java API as a separate Java module
# what does the word ‘require’ do?
ava 9 introduced a new module system in which a module-info. java file names a module and specifies its dependencies ( requires ) and public API ( exports ). The requires clause lets you specify dependencies on other modules.
# How do we bring another module into the file the we are working in?
A requires module directive specifies that this module depends on another module — this relationship is called a module dependency. Each module must explicitly state its dependencies
# what do we have to do to make a module available?
 : Concept: Describe our module filename
 : Concept: Describe our module filepath
 : Code our module descriptor file: module-info. java
 : Add code to our module
 : Compile our module
 : Run our modul
## Things I want to know more about
i need to know more about modul
