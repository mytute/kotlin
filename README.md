# Kotlin programming tutorial

## Content

[hello world program](#hello-world-program)    
[VAR, VAL, INTEGER, BOOLEAN](#var,-val,-integer,-boolean)    
[ARITHMETIC OPERATORS](#arithmetic-operators)        
[DECIMAL NUMBERS](#decimal-numbers)    
[STRINGS](#strings)        
[LOGICAL AND COMPARISON OPERATORS](#logical-and-comparison-operators)    
[IF CONDITIONS](#if-conditions)    
[User Input and NULL values](#user-input-and-null-values)    
[Array](#array)        
[While loop](#while-loop)        
[For loop](#for-loop)        
[LIST](#list)    
[When](#when)        
[Function](#function)    
[VARARG, DEFAULT AND NAMED PARAMETERS](#vararg,-default-and-named-parameters)    
[Class](#class)    
[INHERITANCE](#inheritance)        
[VISIBILITY MODIFIRES](#visibility-modifires)
[ABSTRACT CLASSES](#abstract-classes)    
[CONSTRUCTOR OVERLOADING AND FUNCTION OVERLOADING](#constructor-overloading-and-function-overloading)    
[OBJECTS AND COMPANION OBJECTS](#objects-and-companion-objects)       
[OBJECTS](#objects)    
[companion object](#companion-object)    
[ANONYMOUS CLASSES](#anonymous-classes)    
[EXCEPTIONS](#exceptions)    
[LAMBDA FUNCTIONS](#lambda-functions)    
[GENERICS](#generics)    

### why you should lear Kotlin
1. Complete mull safety. (have to specially create null objects)
2. Use all java libraries in Kotlin, too. (because same bitecode)
3. Kotlin has coroutines. ??
4. Less conde in Kotlin.


install intellij ide
[click] File > [click]  New > [click]  Project > [select] Kotlin and [select] JVM|IDEA
[click] Next > [input] "Project name" and "Project location"  and "Project SDK" > [click] "Finish" .

the import file is (Project_Name >src) src file. by r-clicking there we can add files.
eg: [r-click] on "src" > [select] "New" > [select] "Kotlin File/Class" > [input] file name > [select] file or class etc..
    [input] enter key.

### hello world program

``` kotlin
fun main () {
    println("Hello World!");
}
```

### VAR, VAL, INTEGER, BOOLEAN

``` kotlin
fun main() {
    println("Hello World");

    // define variable
    var myVariable: Int = 5 // we can write without types too.
    var booleanVeriable: Boolean = true;
    val constantVariable : Int = 10 // variable value can't be change **
    println(myVariable);
    println(constantVariable);
    println(booleanVeriable);
    println("The value of our variable is : $myVariable ")
    println("The value of our variable is : ${myVariable} ") // curly brace for write operators inside

    // assign value to variable
    myVariable = 1 ;
    println("The value after assign : $myVariable ");
}
}
```

###  ARITHMETIC OPERATORS

```kotlin
fun main() {
    val x= 15
    var y= 7
    val add = x + y
    println(add)
    println("The add value is ${x+y}")
    println(15+7)
    println(15-7)
    println(15*7)
    println(15/7) // result be a hole number. because both numbers are integer.
    println(15.0/7) // result be a decimal number.
}
```

### DECIMAL NUMBERS

to get decibel number as operator result we have to convert input number to decibel too.

float  number 32bit(4 bytes)
double number 64bit(8 bytes)

```kotlin

fun main() {
    val x :Float = 15F
    val x1 : Float = 15F    // to convert float
    val x2 : Float = 15.0F  // to convert float
    val x3         = 15.0   // to convert double
    var y = 7

    println("The divide result value is ${x / y}")

}

```

### STRINGS

string conclude with many method that can see with shortcut ctr+space

```kotlin
fun main() {
    val x:Int = 10
    val string = "this is an example text" // define string
    println("Our string is: $string")
    println("Our string is: ${string.toUpperCase()}") // concatenate string

}
```

### LOGICAL AND COMPARISON OPERATORS

```kotlin

fun main() {

     val x:Int = 4
     val y:Int = 5

    println(x == y) // false
    println(x >  y) // false
    println(x <  y) // true
    println(x >= y) // false
    println(x != y  &&  x <  y ) // true  && > ||  priority order **
    println(x != y  ||  x >  y ) // true
    println(!(x >  y) ) // true

}

```

### IF CONDITIONS

```kotlin

fun main() {

     val x:Int = 4
     val y:Int = 5
     val z:Int = if(x==y) 3 else 4 // for one command no need curly braces

    if(x<y){
        println("x less than y")
    }else if(x>y){
        println("x bigger then y")
    }else{
        println("all above conditions  got false")
    }

    println("this will always executed")
    // result > "x less than y"

    // another way to write if condition
    val z = if(x<y) 3 else 4
    println("one line condition result $z")
}

```

### User Input and NULL values

```kotlin

fun main() {

    val userInput = readLine() // this line will block the code here

    println("You entered $userInput")

    /* we have to use "?" mark to escape null value convert to uppercase  **/
    println(userInput?.toUpperCase())

    /* we have to use manual null escape for following operator.
    * because to escape null -5
    * but anyway following code will crash for letter input **/
    //println(userInput?.toInt()-5)
    if (userInput != null)
        println(userInput.toInt()-5) // now no need "?" at the end of userInput

}

```


### Array

```kotlin

fun main() {

    // create a array
    // we can't change size after define array
    // array's are immutable
    val myArray = arrayOf("1 value", "name", "age")

    println(myArray); // java.lang.String;@3b6eb2ec array address
    println(myArray[0]); // "1 value"

}

```

### While loop

```kotlin

fun main() {

    val myArray = arrayOf("hello", "guys", "whats up")
    val arrayLength = myArray.size; // get length of array

    var i =0;
    while (i<arrayLength){
        println(myArray[i]);
        i++ // i--
    }
}

```


### For loop

```kotlin

fun main() {

    val myArray = arrayOf(1,2,3);
    for (i in myArray){
        //println(i) // 1,2,3
    }

    // for loop in range 1 to 3 numbers
    for (i in 1..3){
        //println(i) // 1,2,3
    }

    // for loop in range 3 to 1 numbers
    for (i in 3 downTo 1){
        //println(i) // 3,2,1
    }

    // for loop in range 6 to 1 numbers by step 2
    for (i in 6 downTo 1 step 2){
        println(i) // 6,4,2
    }

    // for loop in range a to b in alphabet
    for (i in 'a'..'c'){
        println(i) // a,b,c
    }

    // find max of array using for loop
    var max = myArray[0];
    for(item in myArray){
        if(item > max){
            max = item
        }
    }
    println("max value of array : $max");

}

```


### LIST

```kotlin

fun main() {

    val myArray = arrayOf(1,2,3)
    myArray[0]=0;
    println(myArray[0])

    val myList = listOf(1,2,3)
    // myList[0]=0; normal list's are mutable. can't change value

    val myImmutableList = mutableListOf(1,2,3)
    myImmutableList[0]=0; // mutable list

    /* list can change size *********** */
    myImmutableList.add(4)
    myImmutableList.remove(2) // remove by value
    myImmutableList.removeAt(1) // remove by index

    // list can print directly
    println(myImmutableList)
}

```


### When

```kotlin

fun main() {

    val age = readLine()?.toInt();

    if(age in 0..5){
        println("You're a young kid");
    }else if (age in 6..17){
        println("You're a teenager");
    }else if (age == 18){
        println("Finally, you're 18!")
    }else if (age == 19 || age == 20){
        println("You're a young adult")
    }else if (age in 21..65){
        println("You're an adult")
    }else {
        println("You are old")
    }

    // just simplify in condition

    when(age){
        in 0..5   -> println("You're a young kid")
        in 6..17  -> println("You're a teenager")
              18  -> println("Finally, you're 18!")
        19 , 20   -> println("You're a young adult") // eq to 19 or 20
        in 21..65 -> println("You're an adult")
        else      -> println("You are old")
    }

   // extra
    val x = 6
    when(age){
        in 0..5   -> if (x == 3){ // with another value conditions
            println("You're a young kid")
        }
        in 6..17  -> { // for more command we have to use cruly brases
            println("You're a teenager")
            println("You're a teenager")
        }
        else      -> println("You are old")
    }

}

```

### Function

```kotlin

fun main() {
    // call the function
    printLine()

    // call with parameters
    val x = 3;
    calculateValue(x, 2)

    // call with return value

}


fun printLine(){
    println("call from main")
}

fun calculateValue(base:Int, exponent: Int){
    var result = 1;
    for(i in 1..exponent){
        result *= base
    }
    println("$base to the power of $exponent is $result")
}

```



### VARARG, DEFAULT AND NAMED PARAMETERS

```kotlin

fun main() {

    // VARARG
    val max1 = getMax(1,2,3,4,5)
    println("get max from argument array $max1")

    val array = intArrayOf(10, 20, 25)
    val max2 = getMax(1,2,3,4,*array) // add another argument using array
    println("get max from argument array $max2")

    search("How to became a good programmer", "Google")

    // DEFAULT
    searchWithDefaultParam("How to became a good programmer")

    // NAMED PARAMETERS
    searchWithUnorderParam(searchEngine = "Bing", search = "How to became a good programmer")
}

fun search(search:String, searchEngine: String){
    println("Searching for $search on $searchEngine")
}
fun searchWithDefaultParam(search:String, searchEngine: String = "Google"){
    println("Searching for $search on $searchEngine")
}

fun searchWithUnorderParam(search:String, searchEngine: String){
    println("Searching for $search on $searchEngine")
}

fun getMax(vararg numbers:Int):Int{
    var max = numbers[0];
    for (number in numbers){
        if (number > max){
            max = number
        }
    }
    return max
}

```


### EXTENSION FUNCTION

```kotlin

fun main() {

    println("Please enter a number")
    val input = readLine()?.toInt()

    if(input != null){
        if(input.isPrime()){
            println("$input is a prime number")
        }else{
            println("$input is a prime number")
        }
    }

}

/* Extension Function
 * we can add function to built function in kotlin
 */
fun Int.isPrime():Boolean{
    // this = input value
    for (i in 2 until this ){  // until = 2..this-1

        if (this % i==0){  // % return
            return false
        }
    }
    return true;
}

```


### Class
to create class on new file
"src" file [r-click] > "New" > "Kotlin File/Class" > [select] class & and name of class.    
but we can create class with "class" keyword in any ware.    

```kotlin

fun main() {

    val myRect = Rectangle(5,4)

    println("area ${myRect.area()}")
    println("perimeter ${myRect.perimeter()}")
    println("isSquare ${myRect.isSquare()}")

}



class Rectangle (  // by adding "()" brackets can create constructor
        val width:Int,
        val height:Int
){
    val pi = 3.1 // common value for class

    init{
        println("Rectangle created with width= $width and height= $height")
        println("init area ${area()} ")
    }

    fun area() = width * height

    fun perimeter() = 2*width +2*height

    fun isSquare() = width==height
}

```

### INHERITANCE

Rectangle class > Shape class(supper)

```kotlin
fun main() {

    val myRect = Rectangle(5,4)

    println("area ${myRect.area()}")
    myRect.printName()

}

class Rectangle (
        val width:Int,
        val height:Int
):Shape("rectangle"){ // call supper class **********************
    val pi = 3.1 // common value for class

    init{
        println("Rectangle created with width= $width and height= $height")
    }

    fun area() = width * height

}

/*  supper class ------------------------------------  */
open class Shape( // add "open" keyword for supper class
        var name:String
){
    init {
       println("This is the supper class $name")
    }
    fun printName(){
        println("This is the supper class $name ")
    }
}


```

### VISIBILITY MODIFIRES

```kotlin

private : available in inside class
public : default available in outside/inside class
protected : available in insideclass/insubclasses

```

### ABSTRACT CLASSES

Abstract  class just for organise code.

1. create a regular class > inherit abstract class > add "override" keyword for
2. create a abstract class > define abstract method eg : abstract fun area()    
3. create instance for regular class. through it can call abstract class methods too.

```kotlin

fun main() {


    var react = Rectangle(2,5)
    react.area()

}

class Rectangle (
        val width:Int,
        val height:Int
):Shape("rectangle"){ // call supper class *********
    val pi = 3.1 // common value for class

    init{
        println("Rectangle created with width= $width and height= $height")
    }

    override fun area() = width * height

}

/*  supper class ------------------------------------  */
abstract class Shape( // add "abstract" keyword for
        var name:String
){
    init {
       println("This is the supper class $name")
    }
    abstract fun area():Int

    fun printName(){
        println("This is the supper class $name ")
    }
}


```

###  CONSTRUCTOR OVERLOADING AND FUNCTION OVERLOADING

```kotlin
fun main() {


    var react = Rectangle(2,5)
    react.area();

    // function overload *******************************************************
    var react1 = Rectangle(2,5)
    var react2 = Rectangle(3,5)
    var react3 = Rectangle(4,5)
    println("max area with two argument ${maxArea(react1,react2)}")
    println("max area with tree argument ${maxArea(react1,react2, react3)}")


}

// maxArea function with 2 argument
fun maxArea(shape1:Shape, shape2:Shape):Int{
     val areaShape1 = shape1.area()
     val areaShape2=shape2.area()
     return if(areaShape1> areaShape2) areaShape1 else areaShape2
}

// maxArea function with 3 argument
fun maxArea(shape1:Shape, shape2:Shape, shape3:Shape):Int{
    val areaShape2 = maxArea(shape1, shape2)
    val areaShape3= shape3.area()
    return if(areaShape2> areaShape3) areaShape2 else areaShape3
}



class Rectangle ( // primary constructor
        val width:Int,
        val height:Int
):Shape("rectangle"){ // call supper class *********
    val pi = 3.1 // common value for class

    // constructor overload ******************************************************
    // overload constructor param should be unique
    constructor(Width:Int): this(Width, Width)  // create new constructor and call primary constructor
    constructor(Width: Double, Height:Double): this(Width.toInt(), Height.toInt()) // ""
    //constructor(a:Int): this(a, a) // not unique ******

    init{
        println("Rectangle created with width= $width and height= $height")
    }

    override fun area() = width * height

}

/*  supper class ------------------------------------  */
abstract class Shape( // add "abstract" keyword for
        var name:String
){
    init {
       println("This is the supper class $name")
    }
    abstract fun area():Int

    fun printName(){
        println("This is the supper class $name ")
    }
}


```

### OBJECTS AND COMPANION OBJECTS

to create class on new file    
"src" file [r-click] > "New" > "Kotlin File/Class" > [select] object & and name of class.        
but we can create object with "object" keyword in any ware.   

#### OBJECTS

```kotlin

fun main() {

    var myCircle = Circle(2)
    println("area of circle ${myCircle.area()}")

}

class Circle (
        val radius:Int
){
    val pi = 3.1 // common value for class
    // here the problem is for every instance we are creating same value variable.

    init{
        println("Circle created with radius= $radius ")
    }

    // here we can get object value(/function) without create instance(directly)
    fun area() = radius * radius * importantNumbers.pi

}

object importantNumbers{
    val pi = 3.1

    fun someFunction(){

    }
}

```

#### companion object    
instance create inside companion object may be ?     

```kotlin

import kotlin.random.Random

fun main() {

    var myCircle = Circle(2.0)
    println("area of circle ${myCircle.area()}")

    // here we no need to create instance ***
    println("area of circle ${Circle.randomCircle()}")

}

class Circle (
        val radius:Double
){
    // companion object ***
    companion object{
        fun randomCircle():Circle{
            val radius = Random.nextDouble(1.0, 10.0)
            return Circle(radius)
        }
    }
    val pi = 3.1 // common value for class

    init{
        println("Circle created with radius= $radius ")
    }

    fun area() = radius * radius * pi

}

```

### ANONYMOUS CLASSES

normally we can't create instance from abstract class.      
But using anonymous classes we can do it.     

```kotlin
fun main() {

    val myCircle = Circle(5)
    println("area : ${myCircle.area()}")

    val a = 3.0
    val b = 4.0
    val height = 2.0
    val parallelogram = object : Shape("parallelogram", a, b, height){

        init {
            println("Parallelogram created width a= $a, b=$b, height=$height")
        }

        override fun area():Double{
            return a*height;
        }
    }

    // call abstract class as anonymously
    println("Is the parallelogram area : ${parallelogram.area()}")

}

abstract class Shape(
        val name:String
){
    constructor(name: String, vararg dimensions:Double ) : this(name)

    init{
        println("The shape name is : $name")
    }

    abstract fun area():Double
}

open class Circle (
        val radius:Int
):Shape("shp"){

    val pi = 3.1 // common value for class

    init{
        println("Circle created with radius= $radius ")
    }

    override fun area() = radius * radius * pi

}


```
### EXCEPTIONS

If program crash anyware it will not work further commands. So we have to handle it.    
you can use try-catch block in normal way too.

```kotlin

import java.lang.Exception
import java.lang.NumberFormatException

fun main() {

    println("Please enter a number :")
    val input =try{
        readLine()?.toInt()
    }catch (e:NumberFormatException){
        0 // return value to "input" variable
    }finally {
        println("This is from the finally block")
    }
    println("You entered $input")

    // custom exception
    val division = try {
        divide(2.0,0.0)
    }catch (e:DivisionByZeroException){
        println("custom error : $e")
        0.0 // return value to "input" variable
    }
    println("value of division $division")
}

// crate custom exception
class DivisionByZeroException : Exception("You cannot divide by zero. please choose other number")

fun divide(a:Double, b:Double):Double{
    if(b==0.0){
        throw DivisionByZeroException()
    }
    return a/b
}

```
### LAMBDA FUNCTIONS

here we are passing custom function/expression to build in function  

```kotlin

fun main() {

    var list:List<Int> = (1..20).toList()
    println("list : $list")
    list = list.filter { it % 2 == 0 } // "it" is item from list (keyword)
    println("list : $list")

}

```

custom lambda function

```kotlin

fun main() {

    val circle1 = Circle(5)
    val circle2 = Circle(3)
    val circle3 = Circle(6)

    val triangle1 = Triangle(6, 2)
    val triangle2 = Triangle(4, 4)
    val triangle3 = Triangle(2, 6)

    var shapes:List<Shape> = listOf<Shape>(circle1,circle2,circle3,triangle1,triangle2,triangle3)

    // just filter as lambda ***
    //shapes = shapes.filter { it.area() > 5.0 }

    // filter and sort as lambda **
    //shapes = shapes.filter { it.area() > 5.0 }.sortedBy { it.area() }

    // filter  as custom lambda **
    //shapes = shapes.customFilter { it.area() > 5.0 }

    // filter  as custom lambda when we have several parameters  **
    shapes = shapes.customFilter { shape, string -> shape.area() > 5.0 }

    for (shape in shapes){
        println("${shape.name} : Area = ${shape.area()}")
    }


}

// create custom lambda function with EXTENSION function
//fun List<Shape>.customFilter(filterFunction :(Shape) -> (Boolean)):List<Shape>{
//    val resultList:MutableList<Shape> = mutableListOf<Shape>()
//    for (shape:Shape in this){
//        if(filterFunction(shape)){
//            resultList.add(shape)
//        }
//    }
//    return resultList
//}

fun List<Shape>.customFilter(filterFunction :(Shape,String) -> (Boolean)):List<Shape>{
    val resultList:MutableList<Shape> = mutableListOf<Shape>()
    for (shape:Shape in this){
        if(filterFunction(shape, str)){
            resultList.add(shape)
        }
    }
    return resultList
}


// here we put "Shape" class for set type of list of shapes
abstract class Shape(
        val name:String
){
    abstract fun area():Double
}

open class Circle(
         val redius:Int
):Shape("circle"){
    val pi = 3.1
    init {
        println("call circle class in redius:${redius}")
    }
    override fun area():Double = redius * pi
}

open class Triangle(
         val width:Int,
         val height:Int
):Shape("triangle"){
    init {
        println("call triangle class in width:${width} and height:${height}")
    }
    override fun area():Double = width * height / 2.0
}

```

### GENERICS

above custom lambda function is working for only "Shape" type. So let's set that "customFilter"
function work for any "List" of types.    

```kotlin
fun main() {

    val circle1 = Circle(5)
    val circle2 = Circle(3)
    val circle3 = Circle(6)

    val triangle1 = Triangle(6, 2)
    val triangle2 = Triangle(4, 4)
    val triangle3 = Triangle(2, 6)

    var shapes:List<Shape> = listOf<Shape>(circle1,circle2,circle3,triangle1,triangle2,triangle3)

    var intList:List<Int> = (1..20).toList()
    intList = intList.customFilter { n -> n > 2 }
    println("intList : $intList")

    // filter  as custom lambda when we have several parameters  **
    shapes = shapes.customFilter { shape -> shape.area() > 5.0 }

    for (shape in shapes){
        println("${shape.name} : Area = ${shape.area()}")
    }


}

 // create custom lambda function with EXTENSION function and Any Type <T>
 // here we are add <T> after "fun" keyword and other types.
fun <T> List<T>.customFilter(filterFunction :(T) -> (Boolean)):List<T>{
    val resultList:MutableList<T> = mutableListOf<T>()
    for (shape:T in this){
        if(filterFunction(shape)){
            resultList.add(shape)
        }
    }
    return resultList
}

// limit for Type
// fun <T:Number>  : T is limited for Numbers


// here we put "Shape" class for set type of list of shapes
abstract class Shape(
        val name:String
){
    abstract fun area():Double
}

open class Circle(
         val redius:Int
):Shape("circle"){
    val pi = 3.1
    init {
        println("call circle class in redius:${redius}")
    }
    override fun area():Double = redius * pi
}

open class Triangle(
         val width:Int,
         val height:Int
):Shape("triangle"){
    init {
        println("call triangle class in width:${width} and height:${height}")
    }
    override fun area():Double = width * height / 2.0
}


```
