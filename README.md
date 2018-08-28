## R - Basic Syntax
```
>>myString<-"Hello World!"                         -->this will store the value of myString
>>print(myString)           or       >>myString    -->print mystring
```

## R - Script File
```
myString<-"Hello world!"
print(myString)
```
```
Rscript name.R              -->TO run the file using cmd
```

### Comments in R
```
# Enter the comment here
```

## Data Types

```
Logical                 TRUE, FALSE                     >>v<-TRUE
                                                        >>print(class(v))

Numeric                 12.3,2,33                       >><-23.2
                                                        >>print(class(v))

Integer                 2L, 23L, 0L                     >><-2L
                                                        >>print(class(v))

Complex                 3+2i                            >><-3+4i
                                                        >>print(class(v))

Character               'a', 'good', '22.1', 'TRUE'     >><-"TRUE"
                                                        >>print(Class(v))

Raw                     "Hello" is stored as 23 3c      >><-charToRaw("Hello")
                                                        >>print(class(v))
```

## Vectors
```
<!--- create a vector --->
apple<-c('red','green',"yellow")
print(apple)
<!---Get the class of the vector--->
print(class(apple))
```
When we execute the above code, it produces the following result-->
```
[1] "red"   "green"  "yellow"
[1] "character"
```

## Lists
```
<!---Create a list--->
list1<-list(c(2,3,5),32.1,sin)
<!---Print the list--->
print(list)
```
It produces the following result-->
```
[[1]]
[1] 2 3 5

[[2]]
[1] 32.1

[[3]]
function (x) .Primitive("sin")
```
## Matrices

```
<!---Create a matrix--->
M=matrix(c('a','a','b','c','b','a'),nrow=2, ncol=3,byrow=TRUE)
print(M)
```
It produces the following result-->
```
        [,1]    [,2]    [,3]
[1,]    "a"     "a"     "b"
[2,]    "c"     "b"     "a"
```

## Arrays

```
<!---Create an array--->
a<- array(c('green','yellow'),dim=c(3,3,2))
print(a)
```
It produces the fllowing result-->
```
, , 1

        [,1]        [,2]        [,3]
[1,]    "green"     "yellow"    "green"
[2,]    "yellow"    "green"     "yellow"
[3,]    "green"     "yellow"    "green"

, , 2

        [,1]        [,2]        [,3]
[1,]    "yellow"    "green"     "yellow"
[2,]    "green"     "yellow"    "green"
[3,]    "yellow"    "green"     "yellow"
```

## Factors

```
<!---Create a vector--->
apple_colours<-c('green','green','yellow','red','red','red','green')

<!---Create a factor object--->
factor_apple<-factor(apple_colours)

<!---Print the factor--->
print(factor_apple)
print(nlevels(factor_apple))
```
It produces the following result-->
```
[1] green   green   yellow  red red red green
Levels: green red yellow
[1] 3
```

## Data Frames

```
<!---Create the data frame--->
BMI<-data.frame(
    gender=c("Male","Male","Female")
    height=c(133,154.3,122)
    weight=c(45,43,42)
    Age=c(23,43,21)
)
print(BMI)
```
It produces the following result-->
```
    gender  height  weight  age
1   Male    133     45      23
2   Male    154.3   43      43
3   Female  122     42      21
```

## R Variables

```
Variable name       Validity        Reason
-------------       --------        -------
var_name2.          valid           Has letters, numbers, dot and underscore
var_name%           invalid         Has the character'%'. only dot(.) and underscore allowed
2var_name           invalid         Starts with a number
.var_name, var.name valid           Can start with a dot, but the dot should not be followed by a number
.2var_name          invalid         The starting dot is followed by a number making it invalid
_var_name           invalid         Starts with _ which is not valid
```

## Variable Assingnment

```
<!---Assignment using aqual operator--->
var.1=c(0,1,2,3)

<!---Assignment using leftward operator--->
var.2<-c("learn","R")

<!---Assignment using rightward operator--->
c(TRUE,1)->var.3

print(var.1)
cat("var.1 is ",var.1,"\n")
cat("var.2 is ",var.2,"\n")
cat("var.3 is ",var.3,"\n")
```
It will produce the following result-->
```
[1] 0 1 2 3
var.1 is 0 1 2 3
var.2 is learn R
var.3 is 1 1
```

## Data types of a variable

```
var_x<-"Hello"
car("The calss of var_x is ",(var_x),"\n")

var_x<-34.5
cat("   Now the class of var_x is ",class(var_x),"\n")

var_x<-27L
cat("       Next class of var_x becomes ",class(var_x),"\n")
```
It will produce the following result-->
```
The class of var_x is character
    Now the class of var_x is numeric
        Next class of var_x becomes integer
```
## Finding Variables

```
print(ls())                     -->Shows currently availabe variables
print(ls(pattern="var"))        -->List the variable starting with pattern "var".
print(ls(all.name=TRUE))        -->Variables starting with dot(.) are hidden, to list them
```

## Deleting Variables

```
rm(var.3)                       -->To delete a variable (var.3)
rm(list=ls())                   -->To delete all variables
```

## R - Operations

Types of operations >>
* Arithmetic Operations
* Relational Operations
* Logical Operations
* Assignment Operations
* Miscellaneous Operations

## Arithmetic Operations

```
Let we have two vecotrs-->
                v<-c(2,5.5,6)
                t<-c(8,3,4)

+       Adds two vectors                                print(v+t)              [1] 10.0  8.5  10.0
-       Subtracts 2nd vector from 1st                   print(v-t)              [1] -6.0  2.5  2.0
*       Multiplies both vectors                         print(v*t)              [1] 16.0 16.5 24.0
/       Divide 1st with 2nd                             print(v/t)              [1] 0.250000 1.833333 1.500000
%%      Give the remainder of 1st vector with 2nd       print(v%%t)             [1] 2.0 2.5 2.0
%/%     The result of division of 1st vector with 2nd   print(v%/%t)            [1] 0 1 1
^       1st vector raised to the exponent of 2nd        print(v^t)              [1]  256.000  166.375 1296.000
```

## Relational Operations

```
Let we have two vectors-->
                v<-c(2,5.5,6,9)
                t<-c(8,2.5,14,9)
s
>       Check if element of 1st are grater than 2nd                     print(v>t)              [1] FALSE  TRUE   FALSE  FALSE
<       Check if element of 1st are smaller than 2nd                    print(v<t>)             [1] TRUE   FALSE  TRUE   FALSE
==      Check if element of 1st are equals to 2nd                       print(v==t)             [1] FALSE  FALSE  FALSE  TRUE
<=      Check if element of 1st are smaller than or equals to 2nd       print(v<=t)             [1] TRUE   FALSE  TRUE   TRUE
>=      Check if element of 1st are greater than or equals to 2nd       print(v>=t)             [1] FALSE  TRUE   FALSE  TRUE
!=      heck if element of 1st is not equals to 2nd                     print(v!=t)             [1] TRUE   TRUE   TRUE   FALSE
```

## Logical Operations

```
Let we have two vectors-->
                v<-c(3,0,TRUE,2+3i)
                t<-c(4,0,FALSE,2+3i)

&       Element-wise Logical AND operator
        It combines elements of 1st and 2nd vector and gives an output TRUE if both the elements are true.              print(v&t)              [1] TRUE  TRUE  FALSE  TRUE

|       Element-wise logical OR operator
        It combines elements of 1st and 2nd vector and gives an output TRUE if any one of the elements is true.         print(v|t)              [1] TRUE  FALSE  TRUE  TRUE

!       Logical NOT Operator
        Takes each element of the vector and gives the opposite logical value.                                          print(!v)               [1] FALSE  TRUE  FALSE  FALSE


<!---The logical operator && and || considers only the first element of the vectors and give a vector of single element as output.--->

&&      Logical AND Operator
        Takes first element of both the vectors and gives the TRUE only if both are TRUE.                               print(v&&t)             [1] TRUE

||      Logical OR Operator
        Takes first element of both the vectors and gives the TRUE if one of them is TRUE.                              print(v||t)             [1] FALSE

```

## Assignment Operator

These operations are used to assign values to operators.
```

<- or = or <<-          Left assignment        v1 <- c(3,1,TRUE,2+3i)
                                                v2 <<- c(3,1,TRUE,2+3i)
                                                v3 = c(3,1,TRUE,2+3i)
                                                print(v1)
                                                print(v2)
                                                print(v3)

                        It produces the following output-->
                                                [1] 3+0i 1+0i 1+0i 2+3i
                                                [1] 3+0i 1+0i 1+0i 2+3i
                                                [1] 3+0i 1+0i 1+0i 2+3i

-> or ->>               Right assignment        c(3,1,TRUE,2+3i) -> v1
                                                c(3,1,TRUE,2+3i) ->> v2 
                                                print(v1)
                                                print(v2)

                        It produces the following output-->
                                                [1] 3+0i 1+0i 1+0i 2+3i
                                                [1] 3+0i 1+0i 1+0i 2+3i
```

## Miscellaneous Operator

```
:       Colon Operator
         It creates the series of numbers in sequence for a vector.     v <- 2:8
                                                                        print(v)
%in%    To identify if an element belongs to a vector.                  v1 <- 8
                                                                        v2 <- 12
                                                                        t <- 1:10
                                                                        print(v1 %in% t)
                                                                        print(v2 %in% t)
                                It produces the following output-->
                                                                        [1] TRUE
                                                                        [1] FALSE
%*%     Used to multiply a matrix with its transpose.                   M = matrix( c(2,6,5,1,10,4), nrow = 2,ncol = 3,byrow = TRUE)
                                                                        t = M %*% t(M)
                                                                        print(t)
                                It produces the following output-->
                                                                              [,1] [,2]
                                                                        [1,]   65   82
                                                                        [2,]   82  117
```

## R - Decision Making

if statement            --> if statement consists of a Boolean expression followed by one or more statements.
```
x <- 30L
if(is.integer(x)) {
   print("X is an Integer")
}
It produces the following output-->
        [1] "X is an Integer"
```
if...else statement     --> if statement can be followed by an optional else statement, which executes when the Boolean expression is false.
```
x <- c("what","is","truth")

if("Truth" %in% x) {
   print("Truth is found the first time")
} else if ("truth" %in% x) {
   print("truth is found the second time")
} else {
   print("No truth found")
}

It produces the following output-->
[1] "truth is found the second time"
```
switch statement        --> switch statement allows a variable to be tested for equality against a list of values.
```
x <- switch(
   3,
   "first",
   "second",
   "third",
   "fourth"
)
print(x)

It produces the following result-->
[1] "third"
```

## R - Loops

repeat loop             -->Executes a sequence of statements multiple times and abbreviates the code that manages the loop variable.
```
v <- c("Hello","loop")
cnt <- 2

repeat {
   print(v)
   cnt <- cnt+1
   
   if(cnt > 5) {
      break
   }
}

It produces the following result-->
[1] "Hello" "loop" 
[1] "Hello" "loop" 
[1] "Hello" "loop" 
[1] "Hello" "loop" 
```
while loop              -->Repeats a statement or group of statements while a given condition is true. It tests the condition before executing the loop body.
```
v <- c("Hello","while loop")
cnt <- 2

while (cnt < 7) {
   print(v)
   cnt = cnt + 1
}

It produces the following output-->
[1] "Hello"  "while loop"
[1] "Hello"  "while loop"
[1] "Hello"  "while loop"
[1] "Hello"  "while loop"
[1] "Hello"  "while loop"
```
for loop                -->Like a while statement, except that it tests the condition at the end of the loop body.
```
v <- LETTERS[1:4]
for ( i in v) {
   print(i)
}

It produces the following output-->
[1] "A"
[1] "B"
[1] "C"
[1] "D"
```

## Loop Control Statement

break statement         -->Terminates the loop statement and transfers execution to the statement immediately following the loop.
```
v <- c("Hello","loop")
cnt <- 2

repeat {
   print(v)
   cnt <- cnt + 1
	
   if(cnt > 5) {
      break
   }
}

It produces the following output-->
[1] "Hello" "loop"
[1] "Hello" "loop"
[1] "Hello" "loop"
[1] "Hello" "loop"
```

next statement          -->The next statement simulates the behavior of R switch.
```
v <- LETTERS[1:6]
for ( i in v) {
   
   if (i == "D") {
      next
   }
   print(i)
}

It produces the following optput-->
[1] "A"
[1] "B"
[1] "C"
[1] "E"
[1] "F"
```

## R - Functions

```
<!---Function Definition--->
function_name <- function(arg_1, arg_2, ...) {
   Function body 
}
```

## Built-in Function
```
# Create a sequence of numbers from 32 to 44.
print(seq(32,44))

# Find mean of numbers from 25 to 82.
print(mean(25:82))

# Find sum of numbers frm 41 to 68.
print(sum(41:68))

It will produce the following output-->
[1] 32 33 34 35 36 37 38 39 40 41 42 43 44
[1] 53.5
[1] 1526
```

## User-defined Function
```
# Create a function to print squares of numbers in sequence.
new.function <- function(a) {
   for(i in 1:a) {
      b <- i^2
      print(b)
   }
}
```

## Calling a Function
```
# Create a function to print squares of numbers in sequence.
new.function <- function(a) {
   for(i in 1:a) {
      b <- i^2
      print(b)
   }
}

# Call the function new.function supplying 6 as an argument.
new.function(6)

It will produce the following output-->
[1] 1
[1] 4
[1] 9
[1] 16
[1] 25
[1] 36
```

## Calling a function without an argument

```
# Create a function without an argument.
new.function <- function() {
   for(i in 1:5) {
      print(i^2)
   }
}	

# Call the function without supplying an argument.
new.function()

It will produce the following output-->
[1] 1
[1] 4
[1] 9
[1] 16
[1] 25
```

## Calling the function with argument values(by position and by name)

```
# Create a function with arguments.
new.function <- function(a,b,c) {
   result <- a * b + c
   print(result)
}

# Call the function by position of arguments.
new.function(5,3,11)

# Call the function by names of the arguments.
new.function(a = 11, b = 5, c = 3)

It will produce the following output-->
[1] 26
[2] 58
```

## Calling a function with default argument

```
# Create a function with arguments.
new.function <- function(a = 3, b = 6) {
   result <- a * b
   print(result)
}

# Call the function without giving any argument.
new.function()

# Call the function with giving new values of the argument.
new.function(9,5)

It will produce the following output-->
[1] 18
[1] 45
```

## Lazy evaluation of Function

```
# Create a function with arguments.
new.function <- function(a, b) {
   print(a^2)
   print(a)
   print(b)
}

# Evaluate the function without supplying one of the arguments.
new.function(6)

It will produce the following output-->
[1] 36
[1] 6
Error in print(b) : argument "b" is missing, with no default
```

## R - Strings

Examples of valid Strings
```
a <- 'Start and end with single quote'
print(a)
b <- "Start and end with double quotes"
print(b)
c <- "single quote ' in between double quotes"
print(c)
d <- 'Double quotes " in between single quote'
print(d)

It will produce the following output-->
[1] "Start and end with single quote"
[1] "Start and end with double quotes"
[1] "single quote ' in between double quote"
[1] "Double quote \" in between single quote"
```

Examples of invalid strings-->
```
e <- 'Mixed quotes" 
print(e)
f <- 'Single quote ' inside single quote'
print(f)
g <- "Double quotes " inside double quotes"
print(g)

It produces the following output-->
Error: unexpected symbol in:
"print(e)
f <- 'Single"
Execution halted
```
