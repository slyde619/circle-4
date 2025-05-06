---
transition: slide-left
layout: two-cols
---

# Functions

<v-clicks>

- **What are functions?** Reusable blocks of code that perform specific tasks
- **Function declarations vs. arrow functions**
- **Benefits:** Code organization, reusability, and maintainability

</v-clicks>

::right::

```js {all|1-3|5-7|all}
function greet(name) {
  return `Hello, ${name}!`;
}

// Arrow function equivalent
const greet = (name) => {
  return `Hello, ${name}!`;
};

// How we used functions in our project
function calculateTotal(items) {
  return items.reduce((sum, item) => sum + item.price, 0);
}
```