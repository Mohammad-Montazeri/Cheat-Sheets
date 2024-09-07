#### There are two types of programming languages:
	SERVER side : back-end programs; like: PHP, Java, ...
	client side : front-end programs; like: JavaScript, Angular, React, ...

#### There's also another categorization:
	compiled languages: Like C, C++, C#, Java
	interpreted Languages: like Python, JS

Use a semicolon ';' to end your lines.  
Use backslash '/' to comment a line of code
<hr>

Put a `<script></script>` tag after your `<body></body>` tag and write your inline js codes,
or you can write them in an external .js file and import them like:
```html
<script src:'file.js'></script>
```

Making a variable is like: 
```javascript
	var my_name = 'hello';
    var x, y, z;
	var names = ['me', 'you', 2]
	//creating and accessing arrays is just like lists in python
	//or we can create them like:
	var names = new Array('me', 'you', true)
	//we can change them or sort them later too:
	names[1] = 'Hello'
	var sorted_names = names.sort()
```
You can convert variable types with `parseInt() or parseloat()` commands. Note that *parseInt(str)* is the opposite of `num.toString()`.
Booleans are shown as: `true, false`
We also have another variable type called `undefined`.


## PopUp Messages
One way to show popup messages:
```javascript
alert('my message');
alert('my message' + my_name);
alert(typeof my_name );
```
If you want to have buttons in your message box, use `confirm('message')`. Here is a usage of this kind, you'll learn more about *if, else* sentences later.
```javascript
if (confirm("Press a Button !")) {
    txt = "You Pressed OK !";
} else {
    txt = "You Pressed Cancel !";
}
```
If you want to have a text input in your message box, use `prompt('message', 'default value of text input')` command. Here is how:
```javascript
var txt = "";
var person = prompt("Please Enter Your Name :", "Iman Madaeny");
if (person == null || person == "") {
    txt = "User Cancelled The Prompt !";
} else {
    txt = "Hello " + person;
}
```

In JS, `document` symbolizes the webpage. To write on the page:
```javascript
document.write(my_name)
document.write(my_name.length)
document.write('<br/>')
```

## Function
To make a function:
```javascript
	function my_func(parameters){
		.
		.
		.
		return ...;		// not necessary 
	}
```

Another way to create one-line functions:
```javascript
var x = function(a, b) {return a + b}
var c = x(4, 6);
console.log(c);
// or (not recommended!):
var x = new Function('a', 'b', "return a*b");
var c = x(4, 6);
console.log(c);
```

Another way to create functions is called *arrow functions*:
```javascript
var sum = (a, b) => a + b;
console.log(sum(6, 7))
// or:
const sum2 = (a, b) => {
    a *= 10;
    b *= 10;
    return a + b;
};
console.log(sum2(6, 7))
```

To create a function that runs on its own (without being called), define it in a pair of parenthesis and put another one after it:
```javascript
(function(){
    // codes
})()
```
Like Python, we can give initial values to a function's arguments, so that they can be used when the argument is not valued when the function was called:
```javascript
function sum(a = 0, b = 0){
    // codes
}
sum(10);
```

As an equivalent of *star args* of Python, we can use the keyword `arguments` to have access to the arguments that we're not aware of their numbers. E.g.:
```javascript
function test(){
    for(x in arguments){
        console.log(arguments[x]);
    }
}

test(1, 2, 'hi', 'four');
```

To call the function when a `<a></a>` tag is clicked, define it like this:
```html
	<a href='#' onclick='my_func()'> Click! </a>
```

<hr>

Some of numerical operators and their shortcuts:
+ \+
+ \-
+ \*
+ \\
+ %
  + \+= &emsp; \*= &emsp; \-= &emsp; \\=
  + \++	&emsp; \-- 

`.toUpperCase()` is a standard JS functions that changes a text into uppercase format.  


## DOMs and Events
### (document object models)
You can access your html tags by their names, ids, classes, etc. Also, you can change their inner content (what sits between the tag pairs) by `.inerHTML`. for example:

```html
<!-- html -->
<body>
    <input type="number" id="num1">
    <input type="number" id="num2">
    <input type="button" value="sum" onclick="Sum()">
    <h2 id='res'> Result </h2>
</body>
```
```javascript
// javascript
function Sum() {
    var num1 = document.getElementById('num1').value
    var num2 = document.getElementById('num2').value
    var lbl = document.getElementById('res');
    num1 = parseInt(num1)
    num2 = parseInt(num2)
    // parseInt(num1) is the opposite of num1.toString()
    var sum = num1 + num2
    lbl.innerHTML = sum;
}
```

> In addition to **document.getElementById()**, you can use **getElementsByTagName('p')** which returns an array of all \<p> tags in your document.  
> You can use **getElementsByClassName()** as well. Or even you can merge the last two methods by `document.querySelectorAll('a.headers')` which returns all <a> tags that are a subset of *headers* class.  
> To select forms' elements, you can simply use `document.forms['form_id']` which returns all of the elements inside the mentioned specific form.  
> You can change attributes of your selected html object or give it styles like:  
> `document.getElementById('id').src = 'source-address';`   
> `document.getElementsByClassName('class')[0].style.color = 'red';`
> 

<br>

In order to create an html object by JS code, do the following:
```html
<body>
  <div id="div1">
    <p id="p1">This is Paragraph .</p>
    <p id="p2">This is another Paragraph . </p>
  </div>
  
  <script>
    var para = document.createElement("p");
    var node = document.createTextNode("This is New");
    para.appendChild(node);

    var element = document.getElementById("div1");
    element.appendChild(para);  // appends to the end of div1

    var child = document.getElementById('p2');
    element.insertBefore(para, child); // appends right before p2 within div1
  </script>
</body>
```
In order to delete an html object by JS code, do the following:
```html
<body>
  <div id="div1">
    <p id="p1">This is Paragraph .</p>
    <p id="p2">This is another Paragraph . </p>
  </div>
  
  <script>
    var element = document.getElementById('div1');
    var child = document.getElementById('p1');
    element.removeChild(child);
  </script>
</body>
```
In order to delete an html object by JS code, do the following:
```html
<body>
  <div id="div1">
    <p id="p1">This is Paragraph .</p>
    <p id="p2">This is another Paragraph . </p>
  </div>
  
  <script>
    var element = document.getElementById('div1');
    var child = document.getElementById('p1');

    //New element
    var para = document.createElement('p');
    var node = document.createTextNode("This is New");
    para.appendChild(node);

    element.replaceChild(para, child);
  </script>
</body>
```

<br>


### (events)
As you see in the latest codes, `onclick` is one of the mostly used **events** in JS. To use it for the same tag that has been clicked, we use `this`. E.g.:
```javascript
// html
<button onclick='change_lbl()'> Click me! </button>


// JS
function change_lbl() 
{
    this.innerHTML="clicked";
}
```
There are tons of other **events** like *onchange*, *onkeypress*, *onload*, *onmouseover*, *onmouseout*, *onmousedown*, *onmouseup*, and etc. You can use ***this*** to pass the tag itself to the JS function when required. Keep in mind that you can put multiple events on a single tag.  
You don't necessarily have to define the events on the html tag while creating it; You can do it later in your *script* as well. To do so, you have two options: 

1. simply use the object's events like:
    -   ```javascript
        document.getElementById('id').onclick = function_name;
        ```   
2. use an event listener like:
    -   ```javascript
        // inline function
        document.getElementById('mybtn').addEventListener("click",function()  
        {  
          alert('hello iman');  
        });
        ```

    -   ```javascript
        // separate var and function
        var x = document.getElementById('mybtn');
        x.addEventListener("click",hiuser);
        function hiuser()
        {
            alert('hello iman madaeny');
        }
        ```

    -   ```javascript
        // passing a value to the function
        window.addEventListener("resize", function() {
            myWidth(window.innerWidth);
        });

        function myWidth(width) {
            document.getElementById("demo1").innerHTML = width;
        }
        ```

> Note that you can use multiple event listeners to an object, for different or even the same events.  
> Also keep in mind that `window.innerWidth` returns the width of the window, while `Math.random()` returns a random number. 

## BOMs
### (browser object models)
To get the size of browser's window:
```html
<body>
  <p id="demo"></p>
  <script>
    var w =
      window.innerWidth ||
      document.documentElement.clientWidth ||
      document.body.clientWidth;
    var h = window.innerHeight || document.documentElement.clientHeight
      || document.body.clientHeight;

    document.getElementById("demo").innerHTML =
      "Browser inner window width : " + w + ", height : " + h;
  </script>
</body>
```
For the user's monitor size, use `screen.availWidth` and `screen.availHeight` commands. In addition, with respect to the 'https://toplearn.com/c/4628' URL, the following lines respectively return 

- https://toplearn.com/c/4628
- toplearn.com
- /c/4638
- https:

while the last line changes the page to the "https://toplearn.com" webpage.

```javascript
window.location.href
window.location.hostname
window.location.pathname
window.location.protocol
window.location.assign("https://toplearn.com")
```

To use browser's *back* and *forward* buttons, we can do as:
```javascript
// html
<button onclick="goBack()">Back</button>
<button onclick="goForward()">Forward</button>

// JS
function goBack () {
  window.history.back()
}
function goForward () {
  window.history.forward()
}
```

## Animations
Using `setInterval()` and `clearInterval()` functions, we can create timers to help us implement animations. The following code demonstrates how *setInterval(func, step)* calls the *func* function every *step* milliseconds, and how *clearInterval()* stops the process.

```javascript
<body>
    <button type="button" onclick="myMove()">Click me!</button>
    <div id="container" style="width: 500px; height: 500px; background-color: aquamarine; position: relative;">
        <div id="animator" style="width: 50px; height: 50px; background-color: rebeccapurple; position: absolute;">
        </div>
    </div>
</body>

<script>
function myMove() {
    var elem = document.getElementById('animator');
    var pos = 0;
    var time = setInterval(frame, 100);

    function frame() {
        if (pos == 450) {
            clearInterval(time);
        }
        else {
            pos += 25;
            elem.style.top = pos + "px";
            elem.style.left = pos + "px";
        }
    }
}
</script>
```

You can also use `setTimeout(func, milliseconds)` command to perform a function after a while you set in milliseconds. You can also stop it with `clearTimeout()` command.
```html
    <button onclick="myVar = setTimeout(myFunction,5000)">Try it !</button>
    <button onclick="clearTimeout(myVar)">Stop</button>
    <script>
      function myFunction() {
        alert("Salam Azizan ...");
      }

```

## Cookies
This example show the cookies are made and accessed using JS.
```javascript
<body>
  <button onclick="checkCookie()">Set Cookie</button>
  <script>
    function setCookie(cname, cvalue, exdays) {
      var d = new Date();
      d.setTime(d.getTime() + exdays * 24 * 60 * 60 * 1000);
      var expires = "expires=" + d.toGMTString();
      document.cookie = cname + "=" + cvalue + ";" + expires + ";path=/";
    }

    function getCookie(cname) {
      var name = cname + "=";
      var decodedCookie = decodeURIComponent(document.cookie);
      var ca = decodedCookie.split(";");
      for (var i = 0; i < ca.length; i++) {
        var c = ca[i];
        while (c.charAt(0) == " ") {
          c = c.substring(1);
        }
        if (c.indexOf(name) == 0) {
          return c.substring(name.length, c.length);
        }
      }
      return "";
    }

    function checkCookie() {
      var user = getCookie("username");
      if (user != "") {
        alert("Welcome again " + user);
      } else {
        user = prompt("Please enter your name:", "");
        if (user != "" && user != null) {
          setCookie("username", user, 30);
        }
      }
    }
  </script>
</body>

```


## Objects
Classes, also known as objects or JSON (Java Script Object Notation) are created like:
```javascript
var person = {
    name : 'Iman',
    family: 'Madaeny',
    age:30,
    fullName : function()
    {
        return this.name + ' ' + this.family;
    }
};

console.log(person.fullName());		
// console.log() is used to log into the web console
// you can find it in inspect page area of your browser.)
```

For conditional sentences, we use `if(), else if() and else` in the way below. Also keep in mind that for two or more conditional clauses, we use ***&&*** for *and*, **||** for *or*.

```javascript
if (time <= 12) {
    alert('good morning');
} else if (12 < time && time < 17) {
    alert('good afternoon');
} else {
    alert('good evening');
}
```

Conditional operators:
| **Operator** | **Description**                   | **Comparing** | **Returns** |
| :----------- | :-------------------------------- | :-----------: | ----------: |
| ==           | Equal to                          |    x == 8     |       false |
|              |                                   |    x == 5     |        true |
|              |                                   |   x == '5'    |        true |
| ===          | Equal value and type              |    x === 5    |        true |
|              |                                   |   x === '5'   |       false |
| !=           | Not equal                         |   x != '5'    |        true |
| !==          | Not equal value OR not equal type |    x !== 5    |       false |
|              |                                   |   x !== '5'   |        true |
|              |                                   |    x !== 8    |        true |
| >            | Greater than                      |     x > 8     |       false |
| <            | Less than                         |     x < 5     |        true |
| >=           | Greater than or equal to          |    x >= 8     |       false |
| <=           | Less than or equal to             |    x <= 8     |        true |


`Date()` is a standard JS method that returns the current date and time of the system.

Switch case syntax is applied like this:
```javascript
var x = 10;
switch (x) {
    case 1: {
        alert('1');
        break;
    }
    case 2: {
        alert('2');
        break;
    }
    case 3:
    case 4: {
        alert('3 or 4');
        break;
    }
    default: {
        alert('else');
        break;
    }
}
```
In this code, the `break;` is used to prevent other cases from being run.


## Loops
Different ways to loop in a array is shown below. You can also learn the syntax of the **for** loop, which is (start; stop; step).

```javascript
var names = ['one', 'two', 'three'];

for(var i = 0; i < names.length ; i++)
{
    alert(names[i]);
}

var j;
for(j = 0; j < names.length ; j++)
{
    alert(names[j]);
}

var end = names.length;
for(; j < end ;)
{
    alert(names[j]);
    j++;
}

for(n in names)
{
    alert(names[n]);
}
```

You can also use `while()` loops or `do, while()` loops that work like:


```javascript
var i = 1;
while (i < 10) {
    document.write(i + '</br>');
    i++;
}

do {
    document.write(i + '</br>');
    i++;
}
while (i > 10)
```
The difference is, in the *do, while* syntax, the operations run first, and then the condition is checked. In this case, the result of the first loop would be the list of numbers from one to 9, and the second loop will only write 1 on the page.

To achieve the iterative process in an array like above, we can use the following code too:
```javascript
var names = ['one', 'two', 'three'];
var i = 0;
while (names[i]) {
    document.write(names[i]);
    i++;
}
```

We have `break;` and `continue;` commands in loops too.

<br>
<br>

## Error Handling

```javascript
try
{
    // happens if there's no error
}
catch(err)
{
    // happens if there has been an error. the information of the error is saved in the 'err'
    // you can access the error's message by the err.message attribute.
}
finally
{
    // happens under any circumstances. 
}
```

By `throw` method, you can send some messages to the browser's console, so the developers can see that.
```javascript
throw "this is a test message";
throw 404;
```

> In Javascript, all variables created by *var* command are **global**. But if you want to create a **local** variable that is accessible only in its parent block, you can use `let` command that is replaces the old *var* command. E.g.: &emsp; *let IP = 12.0.0.9;*  
> To create a constant variable that can not be altered after it's defined, replace the *var* command with `const`. *Constant* variables, like *let* variables, are local. In addition, they can not be changed or redefined later, but if they were a list or an object, new attributes or indexes can be added to them later.  
> As an equivalent of *append()* method in Python, there is `push()` method in JS. You can use it like:
```javascript
const names = ['one', 'two', 'three'];
names.push('four');
console.log(names)
```

Whenever you want your code to stop from running and continue line by line as you're debugging it, you can put a `debugger;` command in the line where you want to start debugging. Then you can control the code flow from your browser.
 
<hr>

A great example of validation of forms, with 2 different ways:

```html
<body>
    <form name="myForm" action="" method="POST" onsubmit="return myFunction()">
        Name : <input type="text" name="fname">
        <input type="submit" value="submit">
    </form>
</body>

<script>
    function myFunction() {
        debugger;
        var x = document.forms['myForm']['fname'].value;
        if (x == '') {
            alert("Please Enter Name");
            return false;
        }
    }
</>
```

```html
<body>
    <h3>Please enter a number between 1 and 10:</h3>
    Name : <input type="text" id="fname">
    <input type="button" value="submit" onclick="myFunction()">
    <p id="demo" style="color: red;"></p>
</body>

<script>
    function myFunction() {
        // debugger;
        var x, text;
        x = document.getElementById('fname').value;

        if (isNaN(x) || x < 1 || x > 10) {
            text = "input not valid";
            document.getElementById('demo').innerHTML = text;
            document.getElementById('demo').style.color = 'red';
        } else {
            text = "input is Ok!";
            document.getElementById('demo').innerHTML = text;
            document.getElementById('demo').style.color = 'green';
        }
    }
</script>
```

## Constructor
The code below, which creates a function named 'person' as a constructor, is used to create objects (or json) automatically:

```javascript
var iman = {name:"iman", family:'madaeny', age:30}

function person(name, family, age){
    this.name = name;
    this.family = family;
    this.age = age;
    this.fullName = function()
    {
        return this.name + " " + this.family;
    }
}

var ali = new person('ali', 'montazeri', 11);
ali.carName = 'BMW';
console.log(ali)
console.log(ali.fullName())

var people = [];
people.push(new person('mohammad', 'montazeri', 22))
people.push(new person('reza', 'aghajani', 22))
people.push(iman)
people.push(ali)

console.log(people)
```

