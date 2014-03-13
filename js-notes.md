#JavaScript 101

**Programming**: In general, turns data into a sequence of 0s and 1s to communicate with the computer. In JavaScript, data is separated into *values*. 

**Values**: Every value has a type, which determines the role it plays. There are six basic *types* listed below.  

**Types**:

* Numbers - Integers & decimals (e.g. 10, 10.001)
* Strings - characters including spaces. **Must** be contained within quotes (e.g. "How are you today?")
* Booleans - true or false (*keyword*)
* Undefined - means "I don't have a value"
* Objects - see below
* Functions - see below

**Comments**: Used to leave notes within the code but is not included as part of the instructions for the computer to execute.

	// single line comment

	/* Comments that
	are longer than a 
	single line. */

**REPL (read, eval, print, loop)**: takes the code you give it and returns a result. A JavaScript REPL can be accessed in the browser's Developer tools.
(ex. console tab in Chrome's dev tools)

**Expression**: Instructions given to the computer, a fragment of code that  *always produces a value*. Can be any JavaScript type. A value can also be an expression.

There are two types of expressions: those that simply have a value and those that assign a value to a *variable*.

REPL Chrome console example:

	> 1 + 1 //expression
	> 2 //value
	
	> 2 //expression
	> 2 //value
	
	> variableName = 1 + 1 //expression
	> 2 //value

**Statements**: Also instructions given to the computer but *does not always return a value*. Can consist of one or more expressions, keywords, or operators. Statements end with a semi-colon to indicate the end of the instruction.

REPL Chrome console example:

	> 1 + 1; //can be an expression or statement
	> 2 //value
	
	> variableName = "hello"; //can be an expression or statement
	> "hello" //value
	
	> var variableName = "hello"; //statement only - does not return a value
	> undefined 

**Keyword**: Special words reserved in JavaScript to denote specific behaviours. [MDN Keyword List](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Reserved_Words)

**Block Statements**:
Used to group zero or more statements. Enclosed by a pair of curly brackets `{}` to create the block. Single line statements must end in a semi-colon but the block itself does not. Generally used with *control flow statements*.

	var singleLineStatement = "hello"; //needs semi-colon

	if (condition === "something"){
			
		var singleLineStatement = "hello"; //needs semi-colon
		var anotherStatement = "hi"; //needs semi-colon
	
	} //does not need semi-colon
 
##Variables
Used as a container to hold a value and/or grab data to be used later, as needed. The *keyword* `var` is used to *declare* the variable and bring it into existence. The actual variable name is created by you, the programmer. 

To get a variable to hold onto a value, it needs to be *assigned* by using the `=` *operator*. Values can be assigned to a variable using one or two statements.

	var greeting; // no value assigned yet
	greeting = "Hello!"; //value assigned here
		
	//variable declared and value assigned in one line
	var greeting = "Hello!"; 


##Functions

Used to group code/instructions & stores them into descriptive names. Contains reusable chunks of code. Define the function first but it will not run until you call the function. Functions can be used inside other functions.

JavaScript contains many built in functions to make the code do various thing. Example `alert()` creates a pop-up, `prompt()` create a pop-up that asks for user input.

[List of JS methods/functions](http://www.scribd.com/doc/19457597/Javascript-Methods)

###Defining a function 
Create your own functions using the *keyword* `function`.
Functions need to be *defined* to bring it into existence. The name of the function is created by you, the programmer. Choose a descriptive name. 

Functions also have to be *called* in order for it to actually run and execute the instructions. Functions are called by using the function name, followed by parenthesis.  

	alert(); //calling the alert function

There are two ways to define a function, as a *declaration* or as an *expression*. Both work similarly but the browser loads & executes the code slightly different.


####Function declarations
Generally, Javascript executes code from top to bottom but function declarations are loaded *before* any code can run. In this case, the function will execute even if it was called *before* the function was defined.

#####Syntax
	function nameOfFunction(){
		// code to be executed
	}
	
#####Example	
	myFunction(); // calling the function
	
	//defining function
	function myFunction() { 
		alert("This is a function declaration!"); 
	} 
	
####Function Expression

Function expressions load only when the program reaches that line of code. In this case, if you call a function expression *before* it's defined, it will return an error because the computer thinks the function is not defined yet.

#####Syntax
	var nameOfFunction = function(){
		// code to be executed
	};

#####Example	 
	myFunction(); // calling function
	
	//defining function
	var myFunction = function() { 
		alert("This is a function expression!"); 
	};
 
 	> TypeError: undefined is not a function
 	
When using a function expression, the function must be called *after* it’s been defined in order to execute the code.

Here's a helpful [Stack Overflow discussion](http://stackoverflow.com/questions/1013385/what-is-the-difference-between-a-function-expression-vs-declaration-in-javascrip).
 	
#### Self-Executing / Invoking functions

A self-invoking function means a function which invokes immediately after it has been defined. And that's all I'm going to say. 

Read [Self-invoking functions in JavaScript (or Immediately Invoked Function Expressions](http://blog.mgechev.com/2012/08/29/self-invoking-functions-in-javascript-or-immediately-invoked-function-expression/) for more info.

#####Syntax

	(function() {
    	// code to be executed
	}());
	
	// alternative syntax
	
	(function() {
    	// code to be executed
	})();


###Functions and semicolons

**Function declarations** are contained in a `block` denoted by the `{}` so it does not require a semicolon.

	function foo() {
		//do stuff here
	}

**Function expressions** require a semicolon because the function is assigned to the variable which makes it a statement. Statements require a semicolon.

	var foo = function() {
		//do stuff here
	};

**Self invoking functions** also requires a semicolon.

	(function () {
		//do stuff here
	})();

Another useful [Stack Overflow discussion](http://stackoverflow.com/questions/1834642/best-practice-for-semicolon-after-every-function-in-javascript).

###Functions with Parameters/Arguments
Functions can be more flexible and reusable with different options by *passing* a **parameter** into the function. Functions can be used with zero or more parameters.
	
	function myFunction(){
		alert("No parameters!");
	}
	
	function anotherFunction(param1, param2){
		alert("The two parameters are: " + param1 + "," + param2);
	}

When a function is *called*, data that is passed are referred to as **arguments**. These arguments are then passed into the parameters of the function.

	//calling a function with no parameters
	myFunction();
	
	//calling the function and passing two different 
	//sets of arguments into param1 and param2
	anotherFunction("hello", "hi");
	anotherFunction("goodbye", "bye");
	

##Functions and `return`
`return` is a *statement* that specifies the value to be returned by the function. If `return` is used with no expression, it immediately stops at the point where return is called and doesn't executes any of the commands that come after.


### `return` with no expression
	function myMessage(){
		alert("First message.");
		return;
		alert("Second message will not log.");
	}
	myMessage();

Will only alert "First message."

### `return` with an expression

	function makePizza(toppings){
		return toppings;
	}
	
	var myPizza = makePizza("pepperoni & mushrooms");
	alert(myPizza);

The `makePizza` function has been assigned to the variable `myPizza`.  
The argument "pepperoni & mushrooms" is passed into the `toppings` parameter.  The alert will then show "pepperoni & mushrooms".

##Objects
Objects are similar to variables because it can be used to hold values BUT it can hold a *collection* of values instead of just one. An object is also a special kind of data, with *properties* and *methods*.

###Creating an object
Just like *variables*, an *object* needs to be defined first before it can be used.
	
**Defining an empty object**

    var myObject = new Object();
    var myObject = {};
    
Both lines are the same, `{}` is shorthand for `new Object()`

###Adding values to the `object`

*Variables* are called **properties** when they're associated with objects.  
*Functions* are called **methods** when they're associated with objects.

When assigning a value to a variable, the `=` operator is used.  When assigning a value to a property, use a colon instead. Just like variables, the property name can be created by the programmer.

Methods are assigned as a value to the property.

Each property/value pair, also referred to as a key/value pair, must be separated by a comma unless it's the last one.

	var myObject = {};
	
	myObject = {
		myProperty : "value",
		anotherProperty : "another value",
		myMethod : function(){        
			// code to be executed            
		}// closes function
	};

It can also be defined and assigned values in one step.

	var myObject = {
		myProperty : "value",
		anotherProperty : "another value",
		myMethod : function(){        
			// code to be executed            
		}// closes function
	};

###Adding properties & methods to an object

There are many ways (of course) to add new properties and methods to an object after it's been created:
	
	//defining object with 2 properties
	var myDinner = {
		appetizer: "salad",
		main: "chicken"
	};

	
**Adding Properties with Dot Notation**  
*Syntax*: objectName.propertyName	
	
	myDinner.side = "rice";
	myDinner.dessert = "ice cream";
	myDinner.dinnerTime = function(){
		//start eating
	}

**Adding Properties with Square Bracket Notation**  
*Syntax*: objectName["propertyName"]	
	
	myDinner["side"] = "rice";
	myDinner["dessert"] = "ice cream";
	myDinner["dinnerTime"] = function(){
		//start eating
	}
	
[Another handy Stack Overflow discussion](http://stackoverflow.com/questions/1168807/how-can-i-add-a-key-value-pair-to-a-javascript-object-literal).

###Retrieve an item from an object

You can retrieve properties from an object using the same syntax as adding a property.
	
	myDinner.side; // will return "rice"
	myDinner["dessert"]; // will return "ice cream"

###Executing a Method
A method *is* a function, except that it's associated to an object. Calling the method uses the same syntax as calling a function but use *dot notation* to attach it to a specific object.

    myDinner.dinnerTime(); // will run the dinnerTime function
    
### Variables & Objects
Variables can be treated like objects. That means, methods can be associated to a variable, since it is an object too.
	
	var firstname = "Christina";
	
	// apply existing javascript property .length using dot notation
	var numberOfLetters = firstname.length;
	alert(numberOfLetters);


A popular built-in javascript object/method combo is `console.log()`. Instead of using alert(), which can get annoying, `console.log(argument)` will log whatever argument you pass into the browser's console. Very handy when debugging and testing.


##Arrays
Similar to objects because they both hold a collection of values. BUT, arrays hold its values in a numerical index rather than labels.

Think of arrays as egg cartons. All the eggs are in one carton but each egg has its own slot.

Arrays are declared using the *keyword* `var` but *square brackets* are used to hold the values, separated by commas. It can hold any JavaScript value type.

	var eggCarton = [];
	eggCarton = ["chicken egg", "duck egg", "quail egg", "no egg"];
	
Array indexes **ALWAYS** start at **ZERO**. STARTS AT ZERO. ALWAYS.  
The first item in the array has an index of 0. Values in an array can also be assigned to the index number.
	
	eggCarton[0] = "chicken egg";
	eggCarton[1] = "duck egg";
	eggCarton[2] = "quail egg";
	eggCarton[3] = "no egg";

###Adding a new value
	
`push()` is a built-in method use to add an item, which goes to the end of the array.

    eggCarton.push("goose egg");

###Get items from an array

The index number is also used to access the value from the array. In this example, the *second* item of the array will be logged into the browser console.

    console.log(eggCarton[1]);


##Control Flow
By default, statements are executed one after the other, in the order they are written. Control flow refers to techniques used to specify alternate courses for the program flow based on logical decisions. (e.g. if, for, while statements)


###`if` conditional statements

Used to make decisions with your code based on possible circumstances. Starts with the *keyword* `if` followed by round brackets `()` to hold a condition to test. The curly braces `{}` denote a *block statement* to group statements to be performed if that condition is true. If the condition is false, nothing happens.

    if (condition to check for) {
        //statements to be executed if condition is true
    }
    if (3 > 1) {
    	console.log("Three is bigger than 1.");
    }


###`if` / `else` conditional statements

The `else` *keyword* can be added as a fallback block of code that will run if the condition isn't met. It's optional.

    if (5 < 2){
        console.log("Condition is false. This statement will never run.");
    } else {
        console.log("This statement will run instead.")
    }


###`if` / `else if` / `else`/ conditional statements

Test multiple conditions by using `else if` before `else`. There is no limit to the amount of `else if` statements that can be used.
    
    var weather = "sunny";

    if (weather === "snowy") {
        console.log("Ugh.");
    } else if (weather === "sunny"){
        console.log("Yay! Let's go the beach.");
    } else if (weather === "clear"){
        console.log("I can live with that.");
    } else {
        console.log("I don't know what the weather is.")
    }

    > Yay! Let's go the beach.


#### Complex conditionals

Logical operators can be used to create complex conditional statements.

`&&` represents "and"  
`||` represents "or"  
`!`  represents "not" 

	var smallNumber = 1;
	var bigNumber = 100;

	if(smallNumber < 10 && bigNumber > 50){
		console.log("Will log if both conditions are true.");
	} 
	
	if(smallNumber > 10 || bigNumber > 50) {      		
		console.log("Will log if at least one condition is true.");
	}
	 
	if(smallNumber !== 2){
		console.log("Will log because this condition is true.");
	}


##Loops
Loops are used to execute repetitive code for a specified number of times or through a list of values. Loops will execute the same code continuously, using conditional statements to determine when to begin and stop.

###`while` loops
Creates a loop that executes a specified statement and repeats as long as the condition evaluates to true.

**If the condition is never false, the while loop will keep going and crash the browser.**
	
	// declaring index variable
	var i = 0;

	while (i < 3) {
		i++; // increments the value of i by 1 after each loop
  		console.log("The index is " + i);
	}
	
In each iteration, the loop increments `i` by 1.

* first pass: The index is 1
* second pass: The index is 2
* third pass: The index is 3


###For Loops 
Can also be used to repeat a set of instructions. Creates a loop that consists of three optional expressions, enclosed in parentheses and separated by semicolons.
 
    for (start; stop; increment) {
        // statements to run as long as condition is true
    }

    for (var i = 0; i < 5; i++) {
        console.log("The current count of the loop is " + i);
    }
    
The variable name can be anything but using `i` is common because it refers to an index. In this example, the index starts at 0, stops at 4 and adds 1 to the index until the condition is false.


###Loops & arrays 

`for` loops can be used to iterate through all the items within an array. You can't assume that you will always know how many items will be in the array so the `.length` method is used to grab the total number of items in the array.

**Important**: the index variable has to start at 0. Array indexes are **zero based** meaning the first item has an index of 0. 

    var myMeals = ["breakfast", "second breakfast", "lunch", "dinner"];

    for(var i = 0; i < myMeals.length; i++){
        console.log("Would you look at the time. It's " + myMeals[i] + " time.");
    }

Logs:  
It's breakfast time.  
It's second breakfast time.  
It's lunch time.  
It's dinner time. 


---
And that’s all folks!
#####By Christina Truong // [christinatruong.com](http://christinatruong.com)













