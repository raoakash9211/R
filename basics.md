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
