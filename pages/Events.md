---
layout: two-cols
---

# Events & UI Events

<v-clicks>

- **Event listeners:** Code that executes when specific actions occur
- **Common events:** click, submit, keyup, mouseover
- **Cool feature:** Confetti animation on task completion

</v-clicks>

::right::

```js {all|1-5|7-11|13-19|all}
// Basic event listener
document.getElementById('myButton').addEventListener('click', () => {
  alert('Button clicked!');
});

// Keyboard event example
document.addEventListener('keyup', (event) => {
  if (event.key === 'Escape') {
    closeModal();
  }
});

// Our confetti effect on task completion
function completeTask(taskId) {
  markTaskAsComplete(taskId);
  // Trigger confetti animation
  confetti({
    particleCount: 100,
    spread: 70,
    origin: { y: 0.6 }
  });
}
```