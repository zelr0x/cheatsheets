## Object.create(proto, [propertiesObj])
Creates a new object using the provided object `proto` as the prototype of the newly created object. It is a more suitable replacement for the `new` keyword when working with prototypes directly rather than via `class`.

Optional `propertiesObj` parameter is an object which own _enumerable_ properties and _non-enumerable_ properties from its prototype-chain are added to newly created object.

```js
const dog = {
    bark: function() {
        console.log(this.sound);
    }
};

const cyberDog = Object.create(dog);
cyberDog.sound = 'w00f';
cyberDog.bark(); // 'w00f'

dog.isPrototypeOf(cyberDog); // true
cyberDog.prototype; // undefined
cyberDog.__proto__ === dog; // true

dog.prototype; // undefined
dog.__proto__ === Object.__proto__; // false
dog.__proto__ === Object.prototype; // true
```
