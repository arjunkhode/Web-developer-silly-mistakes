# Foolish mistakes I make as a web developer

1. Disadvantages of var
	- var can be reassigned
	- var are either function scoped or globally scoped
	- var leaks outside if statements


1. I forgot to add a closing `div` tag!

1. At one time, I tried to use colon in a strange wrong way in CSS
	```
	a:
	width="100px";
	```
	That's a silly mistake indeed.
	Use the element names followed by braces. Properties are written inside these braces
	and use a colon for the attributes
	```
	a{
	width: 100px;
	}
	```

1. `<link rel="stylesheet" href="./style.css">`
	* Use ./ in the path even if it's in the same folder
	* For stylesheets, the link rel markup has 'href' and not src

1. Meta tags have a name and content. The name of the meta tag is like a title for the meta property and content is the value assigned to that title.
	```
	<meta name="author" content="Arjun Khode"/>
	```

1. Let's settle the right way to write a meta for viewport once and for all
	```
	<meta name="viewport" content="width=device-width, initial-scale=1.0" />
	```

1. In JS, the data attribute can be accessed by dataset, but is it dataSet or dataset?

	Again, is it just dataset or a function call dataset()?
	```
	//It is dataset, and it is a property, not a function
	 	const btn = document.queryselector('.btn');
		console.log(btn.dataset.state);
	```

1. Are the eventListeners camel-case? Is it mousedown or mouseDown? 

	No, the eventListeners are all lowercase
	```
	document.addEventListener('mousedown',function(){...});
	``` 

1. Then again, is it setTimeout or settimeout? I am confused between the eventListener case and standard JavaScript functions case.

	```
	//It is setTimeout(); Standard javascript function names are camelCase
	const tx = setTimeout(function(){console.log("Hi, I am 5 seconds late, sorry.")},5000);
	const paragraphs = document.querySelectorAll('p');
	//Also, many a property names of standard JS structures are camelCase
	element.classList.add('newClass');
	```

1. Speaking of eventListeners, what is the 'change' event?

	The change event is fired for input, select, and textarea elements when a change to the element's value is committed by the user. Unlike the input event, the change event is not necessarily fired for each change to an element's value.

1. Do I use fat arrow function or normal function?

	```
	/*
	A normal anonymous function identifies the calling element as ’this’
	But an arrow function inherits ‘this’ from its parent.
	*/

	//If you want to create a new scope for 'this' and 
	//dive right into the created element, use a normal function.

		const elem1 = document.querySelector('.elem1');
		elem1.addEventListener('click',function(){
		console.log("I am a standard function and my this is:",this);
		//This returns 'elem1' in this example. 
		//The standard function is bounded by the parent which is document.
		
		const elem1 = document.querySelector('.elem1');
		elem1.addEventListener('click',()=>{
		console.log("I am an arrow function and my this is:",this);
		//This returns 'Window' because the parent of the calling statement
		//is Window.
		});
	```
	Check out an [example](https://github.com/arjunkhode/Web-developer-silly-mistakes-/blob/master/fatarrow-vs-standard-functions.html)
	Learn more about it [Here](http://thesagittariusme.blogspot.com/2017/02/es6-arrow-functions-this.html)

1. You can't set background color of a radio button because no such exact property exists for it. You can change the appearance of a radio button but not by setting background color as we normally do for span, etc.

1. For text-overflow:ellipsis to work, width must be in px not %
	```
	text-overflow:ellipsis;
	width: 200px;
	white-space:nowrap;
	overflow:hidden;
	```

1. Let's resolve the issue of how to use a multiple type select input once and for all

	```
		<select name="cars[]" multiple="multiple">
		<option value="volvo">Volvo</option>
		<option value="saab">Saab</option>
		<option value="opel">Opel</option>
		<option value="audi">Audi</option>
		<!-- Note how name="cars[]" has square brackets after it-->
		</select>
		<?php
		$cars = $_POST['cars'];
		print_r ($cars);
		?>
	```

1. `.val()` is a jQuery thing and `.value` is a javaScript thing. It's primarily used to get the values of form elements such as input, select and textarea.

1. A callback function, also known as a 'higher order function' is a function that is passed to another function

1. How to make smooth scrolling in JavaScript?

	```
	//No easy vanilla JS solution found but JQuery version would be:
    $('html, body').animate({scrollTop: $('#element').offset().top}, 'slow');
	```

1. When not to use semicolon?

	It can be omitted if the statement is followed by a line break (or there’s only one statement in a block). 
	The semicolon is only obligatory when you have two or more statements on the same line. You shouldn’t put a semicolon after a closing curly bracket. 
	The only exceptions are assignment statements, such as `var obj = {};`

1. When you use var prefix on a variable, it gets defined in the scope. When no prefix is mentioned, it gets defined as a global variable.

1. You always need to use `this.` prefix to access the original copy of member variables inside ES6 classes.

1. What are first class functions?

	Values can be passed to a function, and the function will return a value. In JavaScript, functions are first-class objects, because they can have properties and methods just like any other object. What distinguishes them from other objects is that functions can be called. In brief, they are Function objects
	
1. Is it e.preventDefault or e.preventDefault()?
	
	It is a function, e.preventDefault()

1. Can you set margin-top and margin-bottom on an inline element?

	No. You can't. Same for padding-top and padding-bottom

1. :checked selector applies to not only checkboxes but also options

1. The translate function cannot translate the element along the z-axis.

1. Are unused style resources still downloaded by the browser?

	No, they are not.
	
1. In the media query @media only screen... the 'only' keyword stops the older browsers from parsing the CSS.

1. Does the screen keyword apply to the device's physical screen or the browser's viewport?

	It applies to the browser's viewport and not the physical screen.
	
1. Overflow:hidden creates a new block formatting context.

1. keygen is a valid HTML tag. It is used for keygeneration in signed certificates

1. Images from img tag in HTML are by default inline. They can be set to block by display:block

1. element.offsetTop gives the distance between top of document and top of element

1. window.scrollY gives the distance of top of viewport from the top of document

1. Template strings:
	```
	   const x = 3;
	   const y = 7;
	   console.log(`${x} + ${y} = ${x + y}`); //produces "3+7=10"
	```
	
### Regarding basic website with Nav

1. To make <a> take full space of li in nav, use:
a{display: block;}

1. adjust line height same as height of li to center text in nav

1. section background was showing 1px at the bottom of the image.
	- Was fixed by assigning display:block to the image
	
1. The angle value and "deg" should have no space in linear gradient.
	```
	linear-gradient(25deg,mistyrose,honeydew);
	```
1. If you are trying to have a fancy linear-gradient on the background for the whole page. Setting a nav with some height would probably cause the page to repeat the gradient after that much height. To avoid this, assuming the gradient is on the body, use the following code on the body:
	```
	  background-repeat: no-repeat;
	  background-attachment: fixed;
	```

# Algorithms related

1. Array.sort() uses quicksort for numbers and mergesort for ascii

1. Whenever you want to pop an array inside a loop, always start from arr.length and decrement to i>0, instead of starting from zero and advancing till arr.length-1, because the length of array gets re-indexed on every pop()

1. ECMAScript 2016 includes an include method for arrays that specifically solves the answer of removing duplicates.
	```
	if(arr.includes(2)) {
	  console.log("2 is already present");
	}
	```

1. Use arr.splice() to delete elements from the original array. Example:
	```
	//delete 3 from arr
	arr=[1,2,3,4,5];
	arr.splice(2,1); //from index 2, delete 1 element
	arr; // [1,2,4,5]
	```

1. The second argument to Array.splice() is not an index. It is the number of elements to remove starting from the index specified by the first parameter.

1. To find index of sub-string in a string, use str.indexOf("sub-string")

1. Strings don't have a forEach function, you have to spread the string [...str].forEach()

1. Difference between for..in and for..of loop:

	Both for..in and for..of statements iterate over lists; the values iterated on are different though, for..in returns a list of keys on the object being iterated, whereas for..of returns a list of values of the numeric properties of the object being iterated.
	
	```
	let list = [4, 5, 6];

	for (let i in list) {
	   console.log(i); // "0", "1", "2",
	}

	for (let i of list) {
	   console.log(i); // "4", "5", "6"
	}
	```
1. By default, the sort() function sorts values as strings.

This works well for strings ("Apple" comes before "Banana").

However, if numbers are sorted as strings, "25" is bigger than "100", because "2" is bigger than "1".

Because of this, the sort() method will produce incorrect result when sorting numbers.

You can fix this by providing a compare function:

	var points = [40, 100, 1, 5, 25, 10];
	points.sort(function(a, b){return a - b});
	
