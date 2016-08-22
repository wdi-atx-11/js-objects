<!--
Creator: Cory Fauver
Market: SF
-->

![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png)

# Javascript Objects

### Why is this important?
<!-- framing the "why" in big-picture/real world examples -->
*This workshop is important because:*

From [Eloquent JavaScript](http://eloquentjavascript.net/04_data.html):

>Numbers, Booleans, and strings are the bricks that data structures are built from. But you can’t make much of a house out of a single brick. Objects allow us to group values—including other objects—together and thus build more complex structures.

If we want to write code of any complexity, we are going to need to understand objects, how to create them, how to manipulate them, how to access data within them, and how to think about them.

### What are the objectives?
<!-- specific/measurable goal for students to achieve -->
*After this workshop, developers will be able to:*

- describe objects as collections of key value pairs.
- demonstrate the ability to access any attribute of an object in two ways - `.` syntax and `[]` syntax
- Display the difference between properties (attributes) and methods. Call an object's methods. Recognize the widespread presence of objects throughout JavaScript syntax (`console.log()`, `$('div').text()`, `string.length`)
- find and display an example of JSON on the web


### Where should we be now?
<!-- call out the skills that are prerequisites -->
*Before this workshop, developers should already be able to:*

- create and manipulate a JavaScript array.
- Skill 2
- Skill 3

### Review

1. Handwrite the syntax for creating an array that contains the number 5, the string 'wdi rocks', and the boolean `true` *in that order*.
2. Handwrite the syntax you'd use to access the string `wdi rocks` within that array.
3. Handwrite the way that you'd add the string 'Monday!' to the end of the list.
4. Handwrite the code you'd use to change the list value `true` to `false`.

## What is an Object?

As of today, we have been writing our Javascript code using mainly functions, Strings, numbers, and Arrays. You've written functions that can print patterns of text, you've accessed the DOM with jQuery, and listened for events on the page. We haven't yet gathered a bunch of strings, numbers, arrays, and functions into a single collection of information. This is where objects come in. An object is **a collection of key-value pairs**. Below is an example of an object.

``` javascript
var car = {
  wheels: 4,
  topSpeed: 110,
  currentSpeed: 0,
  color: 'blue',
  inWorkingOrder: true,
  damage: ['chipped windshield','dented back left bumper', 'passenger window squeaks']
}
```

Here, `wheels` is a **key** and `4` is a **value**. What are the other **key-value pairs**?

Notice that **keys** are short, descriptive names just like variable names. key-value pairs are essentially just variable names and stored values. An object groups the information of many key-value pairs into a meaningful collection.

Notice that in our example, **values** are numbers, booleans, strings, and an array. These are all **attributes** (aka **properties**) of the object. They are the information that describes this object.


#### Accessing the Data in an Object

#### Dot Notation
```javascript
// dot notation
var color = car.color; // blue
var wheelCount = car.wheels; // 4
var operational = car.inWorkingOrder; //true
```

#### Bracket notation

```javascript
// bracket notation
var color = car['color']; // blue
var wheelCount = car['wheels']; // 4
var operational = car['inWorkingOrder']; //true

```

## Methods

An object can hold any data type - numbers, strings, booleans, arrays, functions, and even other objects.

Here's a less boring version of the `car` object that includes some **methods**.

``` javascript
var car = {
  wheels: 4,
  topSpeed: 110,
  currentSpeed: 0,
  color: 'blue',
  inWorkingOrder: true,
  damage: ['chipped windshield','dented back left bumper', 'passenger window squeaks'],
  accelerate: function(){
    if(this.inWorkingOrder && this.currentSpeed < this.topSpeed){
      this.currentSpeed += 10;
    }
  },
  brake: function(){
    if(this.currentSpeed > 0){
      this.currentSpeed -= 10;
    }
  }
}
```

**Methods** are the functions that an object can perform! If we want our object to be able to do things, it will need **methods**.



Objects are all over JavaScript syntax, which we'll see in a moment.



Here's a truncated version of our cohort data.  Take some time to study the structure and the data types within the data object. It's a bit more complex.

```javascript
var data = {
	school: "General Assembly",
	city: "San Francisco",
	course: "Web Development Immersive",
	course_id: "WDI31",
	classroom: "4",
	students: [{
		id: 0,
		last_name: "Baig",
		first_name: "Abbas",
		github_username: "abbasbaigali"
	}, {
		id: 1,
		last_name: "Bak",
		first_name: "Sera",
		github_username: "serabakpak"
	}, {
		id: 2,
		last_name: "Brown",
		first_name: "Alicia",
		github_username: "cabrown91"
	}]
}

```

What data type is the value associated with the `students` key in the `data` object?



-  Based on our experience in class so far and your familiarity with the above object, consider the following as you read further:
  - How many of the properties in `data` are Strings?
 	- How many of the properties are Arrays?
 	- If there is an array, what data type(s) are the elements inside?

The `data` object is a grouping of key & value pairs (known as properties) that describe our class.  

```javascript
school: "General Assembly"
```
In the line above, `school` is the **key** and `"General Assembly"` is the **value**.

To access a property, we can use dot-notation or bracket-notation on the key to have the corresponding value returned.

 ```javascript
 var GA = data.school; //General Assembly
 ```

`GA` has the value `General Assembly`.  

To access an array within an object,  the method is similar to accessing any other property.  The property `students` is an array of Objects.  To access that array and assign it to a variable, we simply perform the following:

 ```javascript
 var studentArray = data.students; //students
 ```
The `data.students` array is now accessible by using `studentArray` instead.
Declaring variables and defining them as portions of a larger object helps us create readable and followable code.  

*We can assume that an Object is a collection of properties (key & value pairs) that all have some sort of relationship and are connected logically to one another.*  

###Quick Challenge
<!--- Make a copy of `data.js` and rename it to `enhancedData.js`-->
- Make a copy of the cohort data
- Add some more properties that logically fit into an object describing our class (address, floor number, and a list of instructors).
- Try to access your new data properties from the console to make sure they work.

If everything worked out, you should have a fully functioning data object, only now with even MORE properties with us to play with!  


##Creating an object
For relatively straightforward and small objects, it is perfectly fine to declare them as a variable and define them, as we did with the data about a cohort.  This is known as a *Literal* object definition.  
Here. I'll make you a flower using the *Literal* method:

```javascript
// Literal Object Definition
var flower = {
	color : "red",
	petals : 32,
	smellsPretty : true
};
```

#### Note: Arrays are special objects! An array is an object with numerical keys.


The Literal definition of an object creates one single object called flower.  There are no other flowers, just that one single object we created. We can access the properties of an object in one of two ways:  

#### Dot Notation
```javascript
// dot notation
var color = flower.color; // red
var petalCount = flower.petals; // 32
var smellsNice = flower.smellsPretty; //true
```

#### Bracket notation

```javascript
// bracket notation
var color = flower['color']; // red
var petalCount = flower['petals']; // 32
var smellsNice = flower['smellsPretty']; //true
```

##Changing an Object's properties
I don't know about you, but I generally like my Lillies yellow. I have also never heard of a lily with 32 petals, holy smokes!  Can we change our `lily` object to better reflect my perfect lily? You bet!

```javascript
// Changing object property values
lily.color = 'yellow';
lily.petals = 6;
```

That's more like it!  To change the value of the lily object properties. we simply access them with dot or bracket notation.  We then follow with an equals and a new appropriate value.  Couldn't be easier!

<img src = https://seniorhikerphotos.files.wordpress.com/2012/06/lilysarina12052301.jpg width = 75%>

##Object Methods
One of the most powerful features of Javascript Objects are Methods.  Methods are *"functions"* that are predefined and built into an object.  We all know and love array Methods like `forEach()`, `map()`, `filter()`, and `reduce()`; these are all Methods of the Array object.  We use arrays so much that Javascript automagically creates them from an Array constructor without us having to instantiate them with `new` like we did above with the flowers.  Thanks, Javascript!

Lets make a simple method in the flower object that outputs to the console whenever we call it.


```javascript
function Flower(){
    this.color = "red";
    this.petals = 32;
    this.smellsPretty= true;
    // Demonstrates a simple method in an object
    this.sniff = function() {
        console.log("Sniff Sniff Sniff!");
    };
}
```

We now have a method inside our flower object called `sniff`.  When we call it, the console will display "Sniff Sniff Sniff!" as predicted.  

Lets add another method that takes an argument and returns a response.

```javascript
function Flower(){
    this.color = "red";
    this.petals = 32;
    this.smellsPretty= true;
    // Demonstrates a simple method in an object
    this.sniff = function() {
        console.log("Sniff Sniff Sniff!");
    };
    // Demonstrates use of arguments with methods
    this.smellsGood = function(answer) {
    	if (answer) {
    		return 'This flower smells amazing!';
    	} else {
    		return 'What a noxious weed!';
    	}
    };
}
```
Methods can also access properties within the object with the `this` identifier rather than using dot or bracket notation.  Check out the method `describe()` below for an example.

```javascript
function Flower(){
    this.color = "red";
    this.petals = 32;
    this.smellsPretty= true;
    this.sniff = function(){
        console.log("Sniff Sniff Sniff!");
    };
    // Demonstrates use of arguments with methods
    this.smellsGood = function(answer) {
    	if (answer) {
    		return 'This flower smells amazing!';
    	} else {
    		return 'What a noxious weed!';
    	}
    };
    // Demonstrates use of local object variables
    this.describe = function() {
        alert("This flower is " + this.color + ".");    
	}
}
```

###Quick Challenge - She loves me, she loves me not...
Create an object method for flower that will play the age old game ['He loves me, he loves me not...'](https://en.wikipedia.org/wiki/He_loves_me..._he_loves_me_not)
- Count down from the petal number down to 1
- Alternately display 'He loves me' or 'He loves me not' to the console for each petal count decrement.
- Display the final phrase with an exclamation; that's the end of the game!


There are many more aspects to objects that we will discover soon.  For now, play with objects and think up some great object examples that we might use in class.

PS. Here is the Literal equivalent of the flower constructor with all of the methods intact:

```javascript
var flower = {
    color: "red",
    petals: 32,
    smellsPretty: true,
    sniff: function(){
        console.log("Sniff Sniff Sniff!");
    },
    // Demonstrates use of arguments with methods
    smellsGood: function(answer) {
        if (answer) {
            return 'This flower smells amazing!';
        } else {
            return 'What a noxious weed!';
        }
    },
    // Demonstrates use of local object variables
    describe: function(answer) {
        alert("This flower is " + this.color + ".");    
    }
}
```



## Section Title

<!-- framing on *how* the workshop will be conducted ("pair programming"/"think pair share"/"I do, you do, we do"/etc) -->
>***Note:*** *This can be a pair programming activity or done independently.*

#### Non-section heading

Lorem ipsum dolor sit amet, consectetur adipisicing elit. Harum fugiat autem voluptate officia voluptatum tempore repudiandae illum libero. Dolor aliquam minima sit velit, quis quisquam delectus explicabo nam id facilis.

<!-- File path -->
**/directory/file-name.js**

```js
// code here
```

###Illustration
<figure>
  <img src="http://www.computerhope.com/jargon/d/dom1.jpg" alt="DOM Tree">
  <br>
  <figcaption>Descriptive caption</figcaption>
</figure>

###Check for Understanding

<details>
  <summary>Thought provoking question</summary>
  <p>Mind-blowing explanation</p>
</details>

## Independent Practice
Refine the skills covered in this workshop with this [lab](#)

## Closing Thoughts
- review objectives & hierarchy of importance
- look ahead & link to future workshops
- clarify expectations and what developers should know by now
- reiterate “the why” with a perspective of your intentions
- create an active recall
- Check for understanding

## Additional Resources
- [MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Introduction_to_Object-Oriented_JavaScript)
- [Tutsplus](http://code.tutsplus.com/tutorials/the-basics-of-object-oriented-javascript--net-7670)
