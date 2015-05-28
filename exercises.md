# Exercises
---

## Closures

Open `exercises/make.html` in a browser. The code will also be placed in this html file.

### "make" library

Build a tag library that creates elements of the following types in the least LOC:  a, div, span, form, h1, h2, h3, h4.

Example usage:

```
var h1 = make.h1();
h1.innerHTML = 'Hello World';
document.body.appendChild(h1);

var a = make.a();
a.href= 'http://canjs.com';
a.innerHTML = 'CanJS';
document.body.appendChild(a);
```

HINTS:
	Code is ‘built’ one statement at a time.
	document.createElement('h1') –  creates and returns an 'h1' element.

## Context

Implement this exercise in `exercises/context_prototypes/index.js`. You can test your code by opening `exercises/context_prototypes/test.html` in a browser.

### DOT()

Write the dot operator as if it was implemented in JS.

```
var Person = function(name) {
	this.name = name;
}

Person.prototype.isPerson = true;

var person = new Person('Smith');
DOT(person, 'name');        //person.name
DOT(person, 'isPerson');    //person.isPerson
```

Hints:

DOT takes the object and the property
DOT must walk up the __proto__ chain
object.hasOwnProperty('PROPERTY_NAME') returns if an object has a 'direct' property.


### DOTCALL()

Write the dot [[call]] operator as if it was implemented in JS.

```
var Person = function(name) {
	this.name = name;
}

Person.prototype.speak = function(){ 
  console.log('Hello! ' + this.name);
}
var person = new Person('Smith');

DOTCALL( obj, propertyName, args );
DOTCALL( person, 'speak' , [] );  //person.speak()
```

Hints:

DOTCALL must retain context
