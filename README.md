# What-I-Learned-In-Week-14
### Linked List
* An object is mutable data. By changing the value of a key, we essentially changed the object. 
``` javascript
const list = {
    head: {
        previous: head,
        value: 3,
        next: {
            previous: head.next,
            value: 5,
            next: {
                previous: head.next.next,
                value: 11,
                next: null,
            }
        }
    }
}
```
---
### Class
Class has a constructor that builds up your object. One issue with inheritance is that if you want the banana, you'll get the gorilla with it.
``` javascript
class Node {
    constructor(value) {
        this.value = value;
        this.next = null;
    }
} 

const node = new Node();
```

Inheritance code will allow the class to inherit the feature. The `super()` class will call the parent class so you don't have to repeat code.
``` javascript
class Animal {
    constructor(name) {
        this.name = name;
    }

    sayHi() {
        return `I'm an animal named ${this.name}`;
    }

    makeNoise() {
        return 'RAWR';
    }
}

class Dog extends Animal {
    constructor(name) {
        super(name);
    }

    sayHi() {
        return super.sayHi() + 'Woof';
    }
}

const bobo = new Dog('bobo')
const result = bobo.makeNoise();
```
---
### Factory Function
The following function will work as an assembly line in a factory and spit out queue's.
``` javascript
const Queue = () => {
  return {
    items: [],

    add: function(value) {
      this.items.push(value);
    },

    remove: function() {
      return this.items.shift();
    },
  }
}
```
---
### JSON
Javascript Object Notation (JSON) is a lightweight data-interchange format. It is easy for humans to read and write. It is easy for machines to parse and generate.
* always use double quotes.
``` javascript
myObj = {name: "John", age: 31, city: "New York"};
myJSON = JSON.stringify(myObj);
fs.writeFile('users.json', myJSON, function(err) {
    if(err) throw err;
})
```
The following syntax is how you request data from a server.
``` javascript
const xhr = new XMLHttpRequest()

xhr.addEventListener('loadend', (event) => {
    const users = JSON.parse(event.target.response);
})
xhr.addEventListener('error', () => {
    console.log('I didn\'t do it! Hmm.')
})

xhr.open('GET', 'http:local//localhost:3000/users');
xhr.send();
``` 

---
### Memoization
Keep track of what you've seen so far by pushing the value as a key into an object.

---
### Recursion
Calling the function in itself with a call stack(9505 max). 

---
### Notes
* `Null` is intentional while `Undefined` is usually an accident.
* Escape hatch for a simple edge case.
* Factory functions.
* `const Node = (value) => ({value, next: null})`
* `New` key word lets JS that it's a class.
* Object composition is the advanced way to use classes.
* `...args` Default constructor - gathers all the arguments and passes them.
* The following code are the node methods that you can access with the require function. Asynchronous programming that you can access JSON while the browser reads the rest of the code.
``` javascript
const fs = require('fs');
fs.readFile('./user.json', (error, data) => {
    const users = JSON.parse(data);
})
```
* `json-server --watch db.json` sets up a server and everything in the JSON file has to be in an object.
* `Array.isArray()` 