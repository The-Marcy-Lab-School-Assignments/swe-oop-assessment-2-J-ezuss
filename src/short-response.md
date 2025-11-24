# Section 2 — Short Response

Write your responses directly in this file. Follow markdown formatting guidelines. Check the rubric.md file to see how your short responses will be graded.

As a quick guide, check the following before submitting:

- [] Answered all parts of every question
- [] No typos or grammar mistakes (use grammarly!)
- [] Accurately uses relevant technical terminology
- [] Uses markdown to enhance readability (preview in VS Code with Command/Control + Shift + V)
- [] Responses are concise and easy to comprehend

---

## Question 1

In your own words, explain what does _encapsulation_ refer to? Why is this concept beneficial when programming?

Provide a code snippet to illustrate _encapsulation_.

## Response 1

---

What encapsulation does is it builds data, and methods work on that data together inside an object or class. It also means hiding internal details so only the important/ necessary parts are exposed. It's useful because it protects data from being changed incorrectly, making code cleaner and easier to manage.
A code example:

```js
class Player {
  #health = 100; // hidden detail
  damageTaken(amount) {
    this.#health -= amount;
  }

  get health() {
    return this.#health; // safe access
  }
}

const player = new Player();
player.damageTaken(45);
console.log(player.health); // 55
```

## Question 2

Explain what the `this` keyword is. Why is the `this` keyword useful?

In the code snippet below, what does `this` refer to?

```js
class Counter {
  constructor() {
    this.count = 0;
  }
  increment() {
    this.count++;
  }
}

const counterA = new Counter();
const counterB = new Counter();

counterA.increment();
counterA.increment();
counterA.increment();

counterB.increment();

console.log(counterA.count);
console.log(counterB.count);
```

## Response 2

---

`this` refers to the object that is currently calling the method. Inside a class, `this` lets you access the object's own properties and methods. The value of `this` is determined by how the function is called, not where it's written. In the code, `this` is referred to by `count`. How it's being referred to, whichever instance is invoking the method.

## Question 3

In your own words, explain what **polymorphism** means in OOP. Provide an example in code that demonstrates polymorphism.

## Response 3

---

What polymorphism means in OOP (object-oriented programming) is that it allows different classes to have methods with the same name but different behaviors. It's useful because you can write code that works on different objects in a general way, and each object will respond in its own style.
A code example would be

```js
class Shape {
  area() {
    return 0;
  }
}

class Square extends Shape {
  area() {
    return 2 * 2;
  }
}

class Circle extends Shape {
  area() {
    return 3.14 * (4 * 4);
  }
}

const shapes = [new Square(), new Circle()];

for (let s of shapes) {
  console.log(s.area());
}
```

You would get different outputs, while using the same method.

## Question 4

You're building a game where players can raise different digital pets: Cats, Dogs, and Birds. All pets have have a `name`, `energy` level, and `happiness` level and can all `sleep`. Cats have the ability to `hunt`, dogs have the ability to `chase`, and birds have the ability to `fly`.

**Part A:** Describe in words how you would use inheritance to organize these classes.

**Part B:** Explain one advantage of using inheritance here instead of creating three completely separate classes.

## Response 4

## Part A

You can make a main **Pet** class that has all the stuff every pet shares, like `name`, `energy`, `happiness`, and a `sleep` function. Then you make other classes like **Cat**, **Dog**, and **Bird** that inherit from **Pet** so you don’t have to rewrite the same code again. Each one just gets its own special action, like cats can `hunt`, dogs can `chase`, and birds can `fly`. This way its more organized and easier to manage.

## Part B

Using inheritance means I don’t have to copy the same stuff like `name`, `energy`, `happiness`, and the `sleep` function into three different classes. I can put all the shared things in one parent class and then **Cat**, **Dog**, and **Bird**, and just reuse it. It makes the code way cleaner, and if I need to fix something, I only fix it once instead of in 3 places. It just saves a lot of time and mistakes.
