---
layout: two-cols
---

# The Document (DOM)

<v-clicks>

- **Document Object Model (DOM):** Browser's representation of HTML
- **Common operations:** Selecting, creating, modifying elements

</v-clicks>

::right::

```js {all|1-2|4-5|7-11|all}
// Selecting elements
const container = document.querySelector('.container');

// Creating elements
const newButton = document.createElement('button');

// Modifying elements
newButton.textContent = 'Click Me';
newButton.classList.add('primary-btn');
container.appendChild(newButton);
newButton.style.backgroundColor = '#3498db';
```