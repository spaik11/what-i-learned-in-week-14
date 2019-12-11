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

---
### Notes
* `Null` is intentional while `Undefined` is usually an accident.
* Escape hatch for a simple edge case.
* Factory functions.
* `const Node = (value) => ({value, next: null})`
* `New` key word lets JS that it's a class.
* Object composition is the advanced way to use classes.
* `...args` Default constructor - gathers all the arguments and passes them.