---
{"dg-publish":true,"permalink":"/yfitpage/js oops/","created":"2025-08-01T05:43:15.441+05:30"}
---


Here is a detailed, easy-to-understand explanation of all the main **OOP (Object-Oriented Programming) concepts in JavaScript**, with simple words and examples.

---

## 1. **Object**

### What it means:

An object is a collection of data (properties) and behavior (methods).

### Example:

```js
const person = {
  name: "John",
  age: 25,
  greet: function () {
    console.log("Hello, my name is " + this.name);
  }
};

person.greet(); // Output: Hello, my name is John
```

---

## 2. **Class**

### What it means:

A class is a blueprint for creating objects.

### Example:

```js
class Person {
  constructor(name, age) {
    this.name = name;
    this.age = age;
  }

  greet() {
    console.log("Hello, my name is " + this.name);
  }
}

const p1 = new Person("Alice", 30);
p1.greet(); // Hello, my name is Alice
```

---

## 3. **Constructor Function**

### What it means:

Before classes (ES6), we used functions to create objects. These are called constructor functions.

### Example:

```js
function Car(brand) {
  this.brand = brand;
  this.drive = function () {
    console.log(this.brand + " is driving");
  };
}

const myCar = new Car("Toyota");
myCar.drive(); // Toyota is driving
```

---

## 4. **this keyword**

### What it means:

`this` refers to the current object you're working with.

### Example:

```js
const user = {
  name: "Sam",
  showName: function () {
    console.log(this.name);
  }
};

user.showName(); // Sam
```

> In a method, `this` refers to the object calling the method.

---

## 5. **Encapsulation**

### What it means:

Encapsulation means keeping data safe inside an object and not letting others change it directly.

### Example with private fields:

```js
class BankAccount {
  #balance = 0; // private

  deposit(amount) {
    if (amount > 0) this.#balance += amount;
  }

  getBalance() {
    return this.#balance;
  }
}

const acc = new BankAccount();
acc.deposit(100);
console.log(acc.getBalance()); // 100
```

---

## 6. **Abstraction**

### What it means:

Abstraction hides complex code and shows only necessary details.

### Example:

```js
class Laptop {
  turnOn() {
    this.#checkBattery();
    console.log("Laptop is turning on");
  }

  #checkBattery() { // private method
    console.log("Battery is good");
  }
}

const myLaptop = new Laptop();
myLaptop.turnOn(); 
// Battery is good
// Laptop is turning on
```

> You don’t know how `checkBattery` works internally, but you can still use `turnOn()`.

---

## 7. **Inheritance**

### What it means:

One class can use (or inherit) the properties and methods of another class.

### Example:

```js
class Animal {
  eat() {
    console.log("This animal eats food.");
  }
}

class Dog extends Animal {
  bark() {
    console.log("Dog barks");
  }
}

const dog = new Dog();
dog.eat(); // from Animal
dog.bark(); // from Dog
```

---

## 8. **Polymorphism**

### What it means:

Same function name but works differently in different classes (overriding).

### Example:

```js
class Animal {
  makeSound() {
    console.log("Some sound");
  }
}

class Cat extends Animal {
  makeSound() {
    console.log("Meow");
  }
}

const a = new Animal();
const c = new Cat();

a.makeSound(); // Some sound
c.makeSound(); // Meow
```

---

## 9. **Prototype and Prototype Chain**

### What it means:

Every JS object has a hidden link to its prototype. If a property is not found in the object, JavaScript looks in the prototype.

### Example:

```js
function Person(name) {
  this.name = name;
}

Person.prototype.greet = function () {
  console.log("Hi, I am " + this.name);
};

const p = new Person("John");
p.greet(); // Hi, I am John
```

> `greet()` is not inside `p` but in `Person.prototype`, which JS finds through the prototype chain.

---

## 10. **Static Methods**

### What it means:

Static methods are called on the class, not on the object created from the class.

### Example:

```js
class MathUtil {
  static add(a, b) {
    return a + b;
  }
}

console.log(MathUtil.add(2, 3)); // 5
```

> You don’t need to create an object to use `add()`.

---

## 11. **Super keyword**

### What it means:

`super` is used to call the constructor or methods of the parent class.

### Example:

```js
class Animal {
  constructor(name) {
    this.name = name;
  }

  greet() {
    console.log(this.name + " says hello");
  }
}

class Dog extends Animal {
  constructor(name) {
    super(name); // calls Animal's constructor
  }

  greet() {
    super.greet(); // calls Animal's greet
    console.log("Dog says woof");
  }
}

const d = new Dog("Tommy");
d.greet();
// Tommy says hello
// Dog says woof
```

---

Let me know if you want these in a downloadable note format (PDF/markdown), or want a short quiz for revision.