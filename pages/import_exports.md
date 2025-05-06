---
info: Javascript modules
---

# JavaScript Modules

### What are JavaScript Modules?

<v-clicks>

- Files that contain related code
- Allow you to organize your code
- Enable code reuse across your application
- Support encapsulation of functionality

</v-clicks>

<v-clicks>

 <div class="pt-12">
    <span class="px-2 py-1 rounded cursor-pointer bg-green-500 text-white">
        Modules make your code maintainable
    </span>
    </div>
    
</v-clicks>

---

# Example 1: Named Exports and Imports

<div grid="~ cols-2 gap-4">
<div>

**formatTime.js**

```js
// Multiple named exports
export function formatDate(date) {
  return date.toLocaleDateString();
}

export function formatCurrency(amount) {
  return `$${amount.toFixed(2)}`;
}

// You can also export variables
export const TAX_RATE = 0.07;
```

</div>
<div>

**app.js**

```js
// Import multiple named exports
import { formatDate, formatCurrency, TAX_RATE } from "./formatTime.js";

const today = new Date();
console.log(formatDate(today));
// Output: current date formatted

console.log(formatCurrency(19.99));
// Output: $19.99

console.log(`Tax rate: ${TAX_RATE * 100}%`);
// Output: Tax rate: 7%
```

</div>
</div>

---

# Example 2: Default Exports and Imports

<div grid="~ cols-2 gap-4">
<div>

**user.js**

```js
// Default export (only one per file)
export default function createUser(name, age) {
  return {
    name,
    age,
    greet() {
      return `Hello, I'm ${name}!`;
    },
  };
}
```

</div>
<div>

**app.js**

```js
// Importing a default export
// You can name it whatever you want
import createUser from "./user.js";

const john = createUser("John", 30);
console.log(john.greet());
// Output: Hello, I'm John!
```

</div>
</div>
