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

<!--- create a vector --->
```
apple<-c('red','green',"yellow")
print(apple)
<!---Get the class of the vector--->
print(class(apple))
```
