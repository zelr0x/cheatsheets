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
