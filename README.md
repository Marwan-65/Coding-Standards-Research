

# Coding Standards for PHP and JavaScript.

In this report we will discuss different coding standards for PHP and JavaScript in terms of style guides and best practices. We will classify the style guides as the general outline that deals with the format of the code, and best practices as the rules that deal more with the behavior of the code.
### 1. PHP Coding Standards

**1.1 Best Practices**
Here are some of the best practices in JavaScript gathered from a variety of sources:

-  **Give Your Scripts Limits:** The `set_time_limit` function restricts the duration of a script’s execution to a specified number of seconds which is 30 by default. A fatal error is raised once that time has passed.
-  **Never Use Functions Inside Loops:** Saves time running the program
	Inappropriate Practice:
	```
	for ($j = 0, $j <= count($array); $j++)
	{
	//code
	}
	```

	Appropriate Practice:
	```
	$count = count($array);
	for ($j = 0; $j < $count;  $j++)
	{
	//code
	}
	```
-   **Naming Conventions:** Use descriptive, lowercase variable and function names with underscores for separation (e.g., `$total_cost`).
-   **Indentation:** Use 4 spaces for indentation to visually represent code blocks.
-   **Braces:** Always use braces for control flow statements (if, else, for, while) even for single-line statements.
-   **Comments:** Include clear and concise comments to explain complex logic or non-obvious code sections.


	

**1.2 Style Guides**

Several style guides offer detailed recommendations for PHP coding. Here are two popular options:

-   **PSR (PHP Standard Recommendation):** A collection of PSRs define coding standards for different aspects of PHP development. PSR-1, PSR-2, and PSR-4 are particularly relevant for general coding practices and here are some of those practices:
	
	- Class constants MUST be declared in all upper case with 		underscore separators. For example:
		```
		<?php
		namespace Vendor\Model;

		class Foo
		{
		    const VERSION = '1.0';
		    const DATE_APPROVED = '2012-06-01';
		}
		```
	-   There MUST be one blank line after the  `namespace`  declaration, and there MUST be one blank line after the block of  `use`  declarations.
	-   Visibility MUST be declared on all properties and methods;  `abstract`  and  `final`  MUST be declared before the visibility;  `static`  MUST be declared after the visibility.
		```
		<?php  
		namespace  Vendor\Package; 
		abstract  class ClassName 
		{ 
			protected  static $foo; 
			abstract  protected  function zim(); 
			final  public  static  function bar() 
			{ 
				// method body 
			} 
		}
		```

-   **WordPress Coding Standards:** A comprehensive set of guidelines specifically for WordPress theme and plugin development and here are some of those practices:
	- Opening and Closing PHP Tags:
		Correct (Single Line):

		```php
		<input name="<?php echo esc_attr( $name ); ?>" />

		```

		Incorrect:

		```php
		if ( $a === $b ) { ?>
		<some html>
		<?php }

		```
	- In a  `switch`  block, there must be no space between the  `case`  condition and the colon.

		```php
		switch ( $foo ) {
		    case 'bar': // Correct.
		    case 'ba' : // Incorrect.
		}

		```

	-	Unless otherwise specified, parentheses should have spaces inside them.

		```php
		if ( $foo && ( $bar || $baz ) ) { ...

		my_function( ( $x - 1 ) * 5, $y );

		```

	-	When using increment (`++`) or decrement (`--`) operators, there should be no spaces between the operator and the variable it applies to.

		```php
		// Correct.
		for ( $i = 0; $i < 10; $i++ ) {}

		// Incorrect.
		for ( $i = 0; $i < 10; $i ++ ) {}
		++   $b; // Multiple spaces.

		```

**1.3 Sample Examples**

**Good Practice:**

PHP

```
function calculateTotalCost($price, $taxRate) {
  $total = $price * (1 + $taxRate);
  return $total;
}

$itemPrice = 10.00;
$taxRate = 0.07;
$totalPrice = calculateTotalCost($itemPrice, $taxRate);

echo "Total cost with tax: $" . $totalPrice;

```


**Bad Practice:**

PHP

```
function calcTotalCost($price, $tax) {  // Short, unclear function name
  $total = $price * (1+$tax);          // Missing space around operator
  return $total;
}

$itemprice = 10;                       // Inconsistent variable naming
$taxrate = .07;                         // Missing decimal point

echo "Total cost: $" . calcTotalCost($itemprice, $taxrate); 

```



### 2. JavaScript Coding Standards

**2.1 Best Practices**
Here are some of the best practices in JavaScript gathered from a variety of sources:

-   **Initialize Variables:** Provide a single place to initialize variables to avoid undefined values
- **Avoid Global Variables:** This includes all data types, objects, and functions. Global variables and functions can be overwritten by other scripts. 
- **Declarations on Top**: For cleaner code and to reduce the possibility of unwanted re-declarations.
-  **Always Declare Local Variables**: Using the `var`, the `let`, or the `const` keyword, otherwise they will become global variables.
-   **End Switches with Defaults**: always write a default case at the end even if you don't deem it necessary
	```
	switch (new Date().getDay()) {  
	case  0:  
	day = "Sunday";  
	break;  
	case  1:  
	day = "Monday";  
	break;  
	case  2:  
	day = "Tuesday";  
	break;  
	case  3:  
	day = "Wednesday";  
	break;  
	case  4:  
	day = "Thursday";  
	break;  
	case  5:  
	day = "Friday";  
	break;  
	case  6:  
	day = "Saturday";  
	break;  
	default:  
	day = "Unknown";  
	}
	```
- **Use `===` Comparison**: The  `==`  comparison operator converts to matching types, but the  `===`  operator forces comparison of values and type.
- **Declare Arrays with  `const`**: To prevent any accidental change of type.
 ```
 let  cars = ["Saab",  "Volvo",  "BMW"];  
cars =  3; // INCORRECT,Changes array to number  


const  cars = ["Saab",  "Volvo",  "BMW"];  
cars =  3; // CORRECT
```

**2.2 Style Guides**
There are many style guides available with the aim of reaching a consistent coding style amongst the team. These are some examples according to [this "Medium" article](https://javascript.plainenglish.io/javascript-style-guides-d5d25df8cb0f)

- **Idiomatic:** Viewed as one of the most popular style guides, it helps readability, maintainability and consistency while being [open-source](https://github.com/rwaldron/idiomatic.js/)

-   **JavaScript Standard Style Guide:** A popular style guide released under an MIT license with recommended conventions for various JavaScript coding aspects ([Github Link](https://github.com/standard/standard)).
-   **Google’s JavaScript Style Guide:** Outlines the coding standards used at Google. The [guide](https://google.github.io/styleguide/jsguide.html) is divided into two parts, one focusing on style rules and the other on language rules. The guide includes an ESLint package.
- **W3Schools JavaScript Style Guide:** Is an important resource utilized by [W3Schools](https://www.w3schools.com/js/js_conventions.asp) highlighting crucial areas such as code formatting, variable declaration, function definition, error handling, and naming conventions.


They all share, for the most part, many basic conventions such as:

 - Use 2 spaces for indentation.
 - Line Length < 80
	  ```
		 document.getElementById("demo").innerHTML =  
	"I am making a margarita.";
	```
 -  Use camelCase variable names (e.g., `totalPrice`).
 - Best place to break is after an operator or a comma.
 - Multiple blank lines not allowed.
	 ```
	  // ✓ ok
	var value = 'hello world'
	console.log(value)

	// ✗ avoid
	var value = 'hello world'
	// blank line
	// blank line
	console.log(value)
	```
 - Add spaces around operators and after commas.
	    
		    ```
		// ✓ ok
		var list = [1, 2, 3, 4]
		function greet (name, options) { ... }
		
		// ✗ avoid
		var list = [1,2,3,4]
		function greet (name,options) { ... }
		```


But some other conventions may be specific to the style guide, for example:
- The W3Schools JavaScript Style Guide has these specific conventions:
	-   Put the opening bracket at the end of the first line.
	-   Use one space before the opening bracket.
	-   Put the closing bracket on a new line, without leading spaces.
		```
		function toCelsius(fahrenheit) {  
		return (5 / 9) * (fahrenheit - 32);  
		}//Example 1
	 
		if (time < 20) {  
		greeting = "Good day";  
		} else {  
		greeting = "Good evening";  
		}//Example 2
		```
	
	- Use simple syntax for loading external scripts (the type attribute is not necessary)
		`<script src="myscript.js"></script>`
	
- The JavaScript Standard Style Guide has these specific conventions:
	-   **Use single quotes for strings** except to avoid escaping.
	```
    console.log('hello there')    // ✓ ok
    console.log("hello there")    // ✗ avoid
    console.log(`hello there`)    // ✗ avoid
    
    $("<div class='box'>")        // ✓ ok
    console.log(`hello ${name}`)  // ✓ ok
    ```
    
	-   **No unused variables.**
	```
	function myFunction () {
    var result = something()   // ✗ avoid
	}
	```
	-   **Trailing commas not allowed.**
    
      var obj = {
        message: 'hello',   // ✗ avoid
      }
    
   -   **Commas must be placed at the end of the current line.**
    
    
      var obj = {
        foo: 'foo'
        ,bar: 'bar'   // ✗ avoid
      }
    
      var obj = {
        foo: 'foo',
        bar: 'bar'   // ✓ ok
      }


**2.3 Sample Examples**

**Good Practice:**

JavaScript

```
function calculateTotalPrice(price, taxRate) {
  const total = price * (1 + taxRate);
  return total;
}

const itemPrice = 10.00;
const taxRate = 0.07;
const totalPrice = calculateTotalPrice(itemPrice, taxRate);

console.log("Total cost with tax:", totalPrice);

```


**Bad Practice:**

JavaScript

```
function calctotalprice(price, tax) {  // Short, unclear function name
  const total = price * (1+tax)        // Missing space around operator
  return total;
}

let itemprice = 10;                   // Unclear variable naming
let taxrate;                     // No Initialization

console.log("Total cost:", calctotalprice(itemprice, taxrate)); // No semicolon

```

## References

 - _W3Schools.com_. (n.d.). https://www.w3schools.com/js/js_best_practices.asp
 - Makerspace. (2024, January 11). 9 Most useful JavaScript style Guides to Write Better code | JavaScript in Plain English. _Medium_. https://javascript.plainenglish.io/javascript-style-guides-d5d25df8cb0f
 - _W3Schools.com_. (n.d.-b). https://www.w3schools.com/js/js_conventions.asp
 - _Google JavaScript Style Guide_. (n.d.). https://google.github.io/styleguide/jsguide.html
 - Standard. (n.d.). _GitHub - standard/standard: 🌟 JavaScript Style Guide, with linter & automatic code fixer_. GitHub. https://github.com/standard/standard
 - _Top 12 PHP Best Practices for Web Developers – eTatvaSoft_. (n.d.). https://www.etatvasoft.com/blog/php-best-practices/
 - _PHP Coding Standards – Coding Standards Handbook | Developer.WordPress.org_. (2019, April 25). WordPress Developer Resources. https://developer.wordpress.org/coding-standards/wordpress-coding-standards/php/#opening-and-closing-php-tags
 - _PSR-2: Coding Style Guide - PHP-FIG_. (n.d.). https://www.php-fig.org/psr/psr-2/
 - Php-Fig. (n.d.). _fig-standards/accepted/PSR-1-basic-coding-standard.md at master · php-fig/fig-standards_. GitHub. https://github.com/php-fig/fig-standards/blob/master/accepted/PSR-1-basic-coding-standard.md

 
 
