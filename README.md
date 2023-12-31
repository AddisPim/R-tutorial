# R-tutorial
 
This Repository was created to provide an introduction to the programming language R, for the use of a class project at Simmons University.

Author: Addis Pimentel

## PLP-1 Getting Started
### History
R is a statistical programming language created and named after statisticians Ross Ihaka and Robert Gentleman. Initially, R was created in 1993 with the purpose of teaching introductory statistics where Ihaka and Gentleman were both professors at, the University of Auckland, New Zealand. R was later released for the general public in June of 1995. Since R was made for statistical analysis, statisticians and data miners are the primary users of this programming language. Its capabilities include but are not limited to data cleaning, exploration, manipulation, and machine learning.


### Installing R
1. Click on this link [Installing R](https://www.r-project.org)
2. After clicking on the link you should see a bold "**download R**" towards the top of the page, click this link.
3. After clicking the link from Step 2, you should see a list of countries with various links, scroll down to your country and choose a CRAN location (a mirror site) by pressing the link.
4. Now you should see several links that say "Download R for[operating system]" Select the link that matches your operating system.
5. Now you will be given the option to download R, for macOS make sure to use the latest version that matches your device.

### Installing RStudio
In order to run R we must download an IDE (Integrated Development Environment), in this case, we will be installing RStudio as our IDE of choice. Visual Studio Code is another IDE commonly used for R, but RStudio provides a more user-friendly interface and includes a larger variety of statistical libraries that can be utilized for R.

The link for Installing RStudio is below:
[Installing RStudio](https://posit.co/downloads/)

### Running R 
We will be writing a simple "Hello World" program in R, to make sure everything is running smoothly.

### Hello World
These instructions were written specifically for macOS users, the instructions will vary per operating system.
1. Once you have finished Installing R and RStudio, open up RStudio.
2. On the top left corner under **File**, hover over **New File** and select **R Script**.
3. Using the R Script, which will be the top left pane in Rstudio (also called the Source Pane), write **"Hello World"** (make sure this is written in double quotation marks). Now run this line of code.
4. The bottom left pane, which is called the Console Pane, is where our output to our code will appear. After following Step 4, you should see the following output.

```R
> "Hello World"
[1] "Hello World"
```

5. Now make sure to save this file by clicking **File**, and **Save As...** and name this file **HELLOWORLD.R**

### Commenting with RStudio
Commenting on your code is essential when writing various lines of code, this helps you keep track of what every line or program does.
To comment in RStudio just use the "#" and proceed to write your comment. This comment won't interfere with the rest of your code. Now you try!

After making your comments, your screen should look something like this:
```R
#This is how to make a comment in your code
"Hello World"
```

### Useful Links for Programming in R
[W3 R Tutuorial](https://www.w3schools.com/r/)

[Introducing R](https://bookdown.org/kdonovan125/ibis_data_analysis_r4/#preface)

[R Tutuorial](https://www.tutorialspoint.com/r/index.htm#:~:text=R%20was%20created%20by%20Ross,the%20R%20Development%20Core%20Team.)

## PLP-2 Data types and naming conventions

R is a weakly and dynamically typed programming language, regularly used by statisticians and Data scientists. What this means is that the data type of a variable can be changed by assigning the variable a different data type. 

For example:
```R
> x = 8
> x = "Bob"
> x
[1] "Bob"
```
The above coding example shows that R allows for mutability within its variables. In the example, we assigned 'x' two different values '8' and 'Bob', the output of x became the last assigned value given to x which is an example of a mutable variable. Due to R's extensive statistical capabilities, some data types within R are immutable but for the most part R is generally mutable. 

### Implicitly Typed R

Implicitly typed languages like R automatically reassign data types when adding or dividing values of two different types.

Example 1:
```R
> a = 6.7896 + 4
> a 
[1] 10.7896
```
Example 2:
```R
> b = 7.755 / 7
> b
[1] 1.107857
```
In the example above we can see a double and integer being adding together and saved into the variable 'a'. When we return the value of 'a' our value is now a double. Since we did not have to reassign the value of 'a' to a double data type and this was automatically done by R, this is an example of widening conversion. We can also see the same result in the second example when we try to divide a double by an integer and are returned a double. 

R also allows us to put different data types into the same list or dictionary. Although R doesn't have a dictionary data type, due to R being implicitly typed, lists can contain different data types within the list, much like a dictionary, therefore you can technically construct a dictionary from a list. 

For example: 
```R
> Dog_info = list(name = "Archie", age = 7)
> Dog_info
$name
[1] "Archie"

$age
[1] 7
```
In the above example we can see that lists allow for different data types, this is an example of storing heterogeneous data. Unlike lists, Arrays are homogeneous meaning it only allows for elements within the Array to have the same data type. Although this depends on what packages you are running in RStudio and your settings, it is still important to follow the homogeneous rules for Arrays. Below is an example of a legal Array within R and its output.

For example: 
```R
> legal_array = array(1:5, dim = c(2, 3))
> legal_array
     [,1] [,2] [,3]
[1,]    1    3    5
[2,]    2    4    1
```

### Variables
R has its own naming conventions as does almost every other programming language. For the variable names in R 

## PLP-3 Loops and Functions in R

### Loops
Due to R's general use being statistical calculations and machine learning, aside from other data science capabilities, it only has 3 loops. The three loops available on R are the 'For Loop', 'The While Loop' and the 'repeat Loop.' These three loops each have their own specific uses within R. 

#### For Loops
The 'For Loop' in R is commonly used to iterate over a sequence of values. For each value in the sequence, R allows you to execute a statement for each value. 

For example:
```R
> for (i in 1:10) {
+   print(i)  
+ }
[1] 1
[1] 2
[1] 3
[1] 4
[1] 5
[1] 6
[1] 7
[1] 8
[1] 9
[1] 10
```
In the above example we used i to iterate over the range of values 1:10. We then applied the print statement for every value within that range which printed out the numbers 1 through 10.

#### While Loops
The 'While Loop' in R is used to run a statement or statments repeatedly until the condition within the loop becomes false [1]. The conition is set within the parameter, inside the parenthesis next to the while statment.

Example 1:
```R
> x = 1
> while (x <= 5) {
+   print(x)
+   x = x + 1
+ }
[1] 1
[1] 2
[1] 3
[1] 4
[1] 5
> 
```

Example 2:
```R
> while (x <= 5) {
+   print(x)
+ }
```

As seen in the second example above, the While Loop will only run if the condition within the parameter is true, if this statement is false the loop will not run. 

#### Repeat Loops
The 'Repeat Loops' are infinite loops that run a statement or statements until a stop conditon is met. The stop condition is placed within the body of the loop with the help of a break statement. If there is no break condition within the loop, then the loop will run infinitely. 

For Example:
```R
> z = 10
> repeat{
+   print(z)
+   z = z + 1
+   if(z > 13){
+     break}
+   }
[1] 10
[1] 11
[1] 12
[1] 13
```
If you run the code from the above example, without the if condition and break statement, you will find that the loop continues printing numbers until you are forced to stop the code from running. 

### Functions
The syntax for functions difer in every programming language, functions in R are declared using the "function()" method. Usually within the parenthesis we will insert our parameters or arguments for the function. This is then followed by curly brackets that go into the body of the function. Functions can also be written without arguments or curly brackets, this is usually done for simple functions that perform specific calculations. We will go over an example of the two different types of functions below. 

Example 1:
```R
> without_function = function(){
+   print("This is a function without arguments.")
+ }
> without_function() #this calls the function
[1] "This is a function without arguments."
```

Example 2:
```R
> product = multiply_function(9, 11)
>   print(product)
[1] 99
```
In example 1, the function does not have parameters and uses curly brackets for the print statment within the body of the function. We then had to call the function for it to print the output of the function. 

In example 2, the function has 2 arguments both 9 and 11. These are then mutiplied together using the multiply_function(). Notice this function does not require curly brackets and it will print the print statement without having to call the function. This is because the multiply_function is specifically designed to perform multiplicative calculations, this is also seen in functions such as mean(), median(), and head(), among many others.

As we saw in example 2, functions in R can input multiple parameters, what we did not show in this example is that R also can intake mutliple parameters of different data types, for example; 

Example 3: 
```R
> multi_function = function(major, year_rank){
+   print(paste("Major:", major))
+   print(paste("Year rank:", year_rank))
+ }
> multi_function("Computer Science", 2)
[1] "Major: Computer Science"
[1] "Year rank: 2"
```
As seen in the above example, using functions in R we can intake multiple parameters of different data types and return multiple values at the same time using multiple print methods within the body of the function. We also used the paste() method to paste a string with the parameters we wanted to print. These are all vital steps in creating functions with multiple data types and multiple return values. 

Another example of R returning multiple values is when using a function to split a string and return both pieces of the string. 

Example 4: 
```R
> split_string = function(input_string) {
+   split_string = unlist(strsplit(input_string, " "))
+   if (length(split_string) >= 2) {
+     return(list(split_string[1], split_string[2]))
+   } 
+ }
> input <- "Jennifer Lopez"
> result <- split_string(input)
> cat("First Name:", result[[1]], "\n")
First Name: Jennifer 
> cat("Last Name:", result[[2]], "\n")
Last Name: Lopez 
```
In example 4 we used the split_string function which takes one argument, in this case; 'input_string.' We used a space character as the separator to split the input string into two parts. In this example our input string was a persons first name and last name. We used the unlist() and strsplit() method to seperate this string into two strings, one for the first name and another string for the last name.

##### Arguments, Parameters, and Local Variables
We previously mentioned arguments, parameters, and local variables, as well as we wrote and saw coding examples for each. What we didn't mention is where these variables are stored within R. When you pass by arguments, parameters, or local variables into to a function, a copy is created on a heap. R manages the memory of these variables automatically. 

##### Scoping Rules
R uses static scoping which means when you refer to a variable, R looks for the variable in the nearest surrounding context or scope. If the variable is not found, R will keep moving outward of the scope until it finds the variable or reaches the global enviornment. This ensures that in variable accessing is based on the location of the variable in the source code. 

##### Side-effects
Side-effects within R can occur in a number of ways. One of the most common side effects is made when a function changes a variable outside of its scope. Another side effect is created when modifying global variables and changing object attributes, among other things. R was essentially created for data manipulation which is often the reason for so many side effects.

#### Recursive Functions
Recursive functions within R are used for solving complex problems that can be broken down into smaller instances of the same problem. We can use recursive functions to calculate factorials.

For example: 
```R
> factorial = function(n){
+   if (n==0){
+     return(1)
+ }
+ result = n*factorial(n-1)
+ return(result)
+ }
> result = factorial(5)
> print(result)
[1] 120
```
In the example above we calculated the factorial of 5 by setting a base case of a factorial of 0 = 1. We then set a recursive case of the factorial of f is f times factorial of (f-1). This is how we broke down this complex problem using a recursive function.

##### Pass-by
All programming languages are Pass-by-reference or Pass-by-value, some are both. R, uses pass-by-value for basic data types.

For example:
```R
> modify_numeric <- function(x) {
+   x = x * 2
+ }
> a = 5
> modify_numeric(a)
> print(a) 
[1] 5
```
In the above example we can see R using pass-by-value to keep the variable 'a' unchanged from the function in which we multiple x by 2. This is because this operation only affects the local copy of x which is within the body of the function. This results in an unchanged value of 5 for the variable 'a'.

##### Sources
- https://www.geeksforgeeks.org/loops-in-r-for-while-repeat/
- https://www.w3schools.com/r/r_functions.asp
- https://www.geeksforgeeks.org/recursive-functions/
- https://www.digitalocean.com/community/tutorials/java-is-pass-by-value-and-not-pass-by-reference

## PLP-4 Control Statements in R

### if/else
As in all programming languages, there are conditional statements that can be used to test whether a condition is True or False. There are also selection control statements which are used to choose between cases. In R, there are several conditional statements, the main one being if/else statements. The 'if' statement must have the conditional statment within parenthesis, if this condition is met then the code will execute the lines of code within curly brackets. Curly brackets are used to delimit code blocks under each condition.

For example:
```R
> age = 2
> if (age < 4){
+   print("This child is a toddler")
+ }else{
+   print("this child is older")
+ }
[1] "This child is a toddler"

> age = 10
> if (age < 4){
+   print("This child is a toddler")
+ }else{
+   print("this child is older")
+ }
[1] "this child is older"
```

As we can see in the example above, the 'if' statement runs and finishes executing when the condition within the parenthesis is met. If this condition is not met, then the 'else' statment runs and executes instead. Certain languages have a "dangling else" problem, this is when an 'else' statement doesn't clearly belong to an 'if' statement. As you have seen in previous examples, if/else statements are each outside of curly brackets but the brackets must not overlap. What may have not been clear is that if/else statements are also reliant on indentation. The indentation determines the scope of the statements, if the syntax does not follow these rules, the code will not run.

#### Multi-Conditional Statements

if/else statments can also be written with multiple conditions, this is written if/else if/else or using specific operators that join conditions. 

For example: 
```R
> age2 = 2
> if (age2 < 4){
+   print("This child is a toddler")
+ }else if(age2 <= 12){
+   print("This person is still a child")
+ }else if(age2 > 12 && age2 < 18){
+   print("this person is a preteen")
+ }else{
+   print("This person is now an adult")}
[1] "This child is a toddler"

> age2 = 15
> if (age2 < 4){
+   print("This child is a toddler")
+ }else if(age2 <= 12){
+   print("This person is still a child")
+ }else if(age2 > 12 && age2 < 18){
+   print("this person is a preteen")
+ }else{
+   print("This person is now an adult")}
[1] "this person is a preteen"

> age2 = 21
> if (age2 < 4){
+   print("This child is a toddler")
+ }else if(age2 <= 12){
+   print("This person is still a child")
+ }else if(age2 > 12 && age2 < 18){
+   print("this person is a preteen")
+ }else{
+   print("This person is now an adult")}
[1] "This person is now an adult"
```

Continuing with our previous example, we can modify the code to include multi-conditonal statments. Multi-condition if/else statements are statements that include multiple 'if' statements. As we see above, we can use 'else if' to create a second or even third condition (or as many as needed) within the program. Another way to construct a multi-conditonal statement is to use the "&&" operator to put two conditions within a single 'if' statement, we saw an example of this above. 

#### Short-Circuit Logic
Short circuit logic is used within programming languages to stop the execution of a multi condition when the first condition is false. We mentioned above the "&&" operator which signifies "AND" in R conditonal statements. We saw an example of using this operator to create a multi conditional statement within parenthesis. What was not clear in this example is that R uses short circuit logic to deicde if running both conditions is necessary. 

For example:
```R
> x = 6
> y = 4
> if (x < 5 && y > 3){
+   print("This condition is met")
+ }else{
+   print("This condition is not met")
+ }
[1] "This condition is not met"
```
As seen in the above example, the code will print the "else" print statement because the condition within the "if" statement is not met. Although the second condition "y > 3" is True, the first condition "x < 5" is False and therefore the entire condition is false and will not execute the print statement. This is an example of short-circuit logic, this is important to remember when making our conditonal statements.

### Selection Control Statements

Selection control statements, as mentioned previously, are used to choose between cases. These are a subtype of control statements. We can use switch statements to choose between multiple cases or conditions.

For example:

```R
> courses = "CS"
> semester_courses = switch(
+   courses, 
+   "CS" = "CS330",
+   "STAT" = "STAT227",
+   "BUS" = "BUS100")
> cat("The course code is", semester_courses)
The course code is CS330
```
In the above example we can see a switch statement being used to find the course code of a specific department or subject. Unlike other languages that have 'switch' statements, in R, cases are contained within parenthesis, this is how the code block is delimited. A 'break' statement isn't necessary unlike in 'Repeat Loops' as mentioned in the previous repository (check "Intro-to-R-part3" to see an example of repeat loops with conditonal statements).  

### Sources 
- https://www.geeksforgeeks.org/control-statements-in-r-programming/#repeatandbreak
- https://r-critique.com/short-circuit-evaluation

## PLP-5 Classes and Inheritance

R in itself is a multi-paradigm programming language, meaning it supports several different programming paradigms. This includes Object Oriented Progragmming (OOP), Functional programming, and the most commonly used paradigm in data analysis; Procedural programming. In this section we will be using some of the OOP functionalities in R. Within R there are S3 and S4 and Reference Classes or R6, these are all very different approaches to OOP. These systems provide ways to define and use objects and classes in R, each with its own set of rules and syntax. We will be diving into the similarities and differences between these systems in the below sections. 

### S3

The S3 system is a straightforward and flexible way to use object-oriented programming. It's like a casual approach where you don't have to define your objects too strictly. You just add labels to your data to tell R what kind of object it is, and write functions that behave differently based on these labels. It's really user-friendly and great for quick tasks or when you don't need very complex structures. This simplicity makes S3 popular, especially for everyday programming and data analysis tasks.

#### Inheritance In S3
Inheritance is informal within this system as we mentioned; this system is known for it's informality. You can simply add another class name to the class attribute of an object. The system then looks for methods in the order of the class names. S3 allows a class like Student to borrow features from another class like Person simply by adding Person to its class description. It's a quick and easy way to share behaviors between classes.

In order to get a clear visual of how S3 functions, let's look at how to create an object and how to inherit step-by-step.

Example: 
```R
# Define the 'Person' class
Person <- function(name, age) {
  list(name = name, age = age)
}
# Set class attribute for 'Person'
class(Person) = "Person"
```
First we will define the 'Person' class or the parent class in which we will later be inheriting from. In the ebove code we are also setting the class attribute for Person. Pay attention to the syntax used in this system to create objects anc classes.



```R
# Define a method for displaying 'Person' details
print.Person <- function(person) {
  cat("Person Name:", person$name, "\nAge:", person$age, "\n")
}
```
We have now created the method for displaying 'Person' details, our method is print.Person which will print Person name and Person age.



```R
# Define the 'Student' class, inheriting from 'Person'
Student <- function(name, age, student_id, course) {
  person <- Person(name, age)
  list(name = person$name, age = person$age, student_id = student_id, course = course)
}

# Set class attribute for 'Student'
class(Student) <- c("Student", "Person")

# Define a method for displaying 'Student' details
print.Student <- function(student) {
  cat("Student Name:", student$name, "\nAge:", student$age, "\nStudent ID:", student$student_id, "\nCourse:", student$course, "\n")
}
```
The above code shows us repeating the same steps as we did to define the 'Person' class and set class attributes, we are now doing this for the 'Student' class in which we will be inheriting from the parent / Person class to the Student / child class. As you can see above, we add person to the Student's class attributes to sllow for inheritance among classes. We then define a method for calling Students in the Students class.


```R
# Instantiate a Person object
Bob <- Person("Bob Smith", 15)
print(Bob)

#printing Person's information using the method defined previously
print.Person(Bob)

# Instantiate a Student object
Lily <- Student("Lily Smith", 16, "54321", "Biology")
print(jane)

#printing Student's information using the method defined previously
print.Student(jane)
print.Student(john)
```
To make sure this is working now that our objects and classes are set up for 'Person' and 'Student', we can initiate a Person object and a Student object. We have created two students, Bob and Lily. We can get the informatino for Bob by either printing the object or calling the methods created earlier, this is done the same for Lily. By calling the methods we have printed out the information for both Bob and Lily and this is an example of inheritance with the S3 system.

### S4
In R, the S4 system is a more organized way of doing object-oriented programming. It's like creating a detailed blueprint for your objects. In S4, you define classes very clearly, specifying exactly what features (called 'slots') each object will have, like giving a person a name and age. This system is great for big projects because it keeps everything well-structured and clear. It's a bit more complex than the simpler S3 system, but it's really good for when you need to make sure your objects follow specific rules and structures.

#### Inheritance with S4

S4 supports formal inheritance, where a class can be defined to inherit from another class, including its slots and methods. This is more similar to traditional OOP languages. In S4, a class such as Student can directly inherit from Person, automatically gaining all its characteristics and methods, plus any new ones specific to Student. It's a more structured and explicit way of building on existing classes.

As we did with S3 systems, it's best to look at an example and observe the different syntax. I will be using an identical example to the one shown for S3.

Example: 
```R
# Define the 'Person' class
Person <- function(name, age) {
  list(name = name, age = age)
}

# Set class attribute for 'Person'
class(Person) <- "Person"

# Define a method for displaying 'Person' details
print.Person <- function(person) {
  cat("Person Name:", person$name, "\nAge:", person$age, "\n")
}

# Define the 'Student' class, inheriting from 'Person'
Student <- function(name, age, student_id, major) {
  person <- Person(name, age)
  structure(list(name = person$name, age = person$age, student_id = student_id, major = major), class = c("Student", "Person"))
}

# Define a method for displaying 'Student' details
print.Student <- function(student) {
  cat("Student Name:", student$name, "\nAge:", student$age, "\nStudent ID:", student$student_id, "\nMajor:", student$major, "\n")
}

# Instantiate a Person object
Bob <- Person("Bob Smith", 15)
print.Person(Bob)

# Instantiate a Student object
Lily <- Student("Lily Smith", 16, "54321", "Biology")
print.Student(Lily)
```
In the above example we went through every step for inheriting from objects. By comparing the code for S3 and S4 we can see the changes in rules and syntax, we will now be looking at Reference classes as the final method for using OOP within R.

### Reference Classes (R6)

Reference Classes, and their more updated version known as R6, bring a different style of object-oriented programming to R. Unlike the earlier S3 and S4 systems in R, where objects are usually copied when modified, Reference Classes work more like how Java does - when you change an object, you change the original one directly, not a copy. This approach is really handy for big, complex projects because it's more efficient with memory. Reference Classes let you have private and public parts, just like in many other programming languages, making them great for building large applications.

#### Inheritance In R6

R6 is similiar to traditional OOP languages due to its reference based inheritance. With R6, a Student class can inherit from a Person class, getting all of Person's properties and methods while adding its own. This is efficient for building complex objects and avoiding code repetition. 

We will now look at an example of inheritance with R6, note: the example will be identical to the ones used for S3 and S4 examples.

```R
# Load R6 package
library(R6)

# Define the 'Person' class
Person <- R6Class("Person",
                  public = list(
                    name = NULL,
                    age = NULL,
                    initialize = function(name, age) {
                      self$name <- name
                      self$age <- age
                    },
                    print_details = function() {
                      cat("Name:", self$name, "\nAge:", self$age, "\n")
                    }
                  ))

# Define the 'Student' class, inheriting from 'Person'
Student <- R6Class("Student",
                   inherit = Person,
                   public = list(
                     student_id = NULL,
                     major = NULL,
                     initialize = function(name, age, student_id, major) {
                       super$initialize(name, age)
                       self$student_id <- student_id
                       self$major <- major
                     },
                     print_details = function() {
                       super$print_details()
                       cat("Student ID:", self$student_id, "\nMajor:", self$major, "\n")
                     }
                   ))

# Instantiate a Person object
Bob <- Person$new(name = "Bob Smith", age = 15)
john$print_details()

# Instantiate a Student object
Lily <- Student$new(name = "Lily Smith", age = 16, student_id = "123456", major = "Biology")
jane$print_details()
```

By comparing all 3 systems of OOP in R, the difference between the syntax and complexity is much more obvious to see. Each system has it's advantages and disadvantages but each of these systems has its own purpose. 

### To summarize: 
- S3: Simple and flexible, great for quick and informal object-oriented coding.
- S4: More formal and structured, ideal for complex and large-scale projects.
- R6 (Reference Classes): Offers reference semantics for efficient memory use, suitable for complex, memory-intensive applications.



























